<template>
	<view>
		<view class="container">
			<view class="list_item flex">
				<span class="sqr_common import">姓名:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入姓名" v-model="submitData.name">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">性别:</span>
				<view class="r-selt">
					<view class="selt" style="justify-content: flex-end;" @click="change('1')">
						<image :src="submitData.gender==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>男
					</view>
					<view class="selt" style="justify-content: flex-end;"  @click="change('2')">
						<image :src="submitData.gender==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>女
					</view>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">联系电话:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入联系电话" v-model="submitData.phone">
				</view>
			</view>
			<!-- <view class="list_item flex">
				<span class="sqr_common import">验证码:</span>
				<view class="sqr_name phoneNum" style="display: flex; justify-content: space-between;">
					<input type="text" placeholder="请输入验证码" style="display: block; width:260rpx;margin: 0;">
					<view class="yzm">获取验证码</view>
				</view>
			</view> -->
			<view class="list_item flex">
				<span class="sqr_common import">选择省县乡:</span>
				<view class="sqr_name">
					<input type="text" :placeholder="address" disabled="true">  
				</view>
			</view>
			<view v-if="!hasRegister">
				<button class="submitBtn" type="submit" @click="Utils.stopMultiClick(submit)">提交</button>
			</view>
			<view v-if="hasRegister">
				<button class="submitBtn" type="submit" style="background: #AAAAAA;">您已注册</button>
			</view>
		</view>
	</view>
</template>

<script>
	import tkiTree from "@/components/tki-tree/tki-tree.vue"
	export default {
		components: {
			tkiTree
		},
		data() {
			return {
				userData:{},
				Router: this.$Router,
				Utils: this.$Utils,
				curr: '',
				address:'',
				submitData:{
					name:'',
					phone:'',
					gender:'',
				},
				hasRegister:false
			};
		},

		onLoad() {
			const self = this;
			
			var res = self.$Token.getProjectToken(function() {
				self.$Utils.loadAll(['getUserData'], self)
			});
			if (res) {
				self.$Utils.loadAll(['getUserData'], self)
			};
		},

		methods: {
			// 确定回调事件
			getUserData() {
				const self = this;
				const postData = {};
				
				postData.tokenFuncName = 'getProjectToken';
				postData.getAfter = {
					city:{
						tableName:'Label',
						middleKey:'city_id',
						key:'id',
						searchItem:{
							status:1
						},
						condition:'=',
						info:['title']
					},
					country:{
						tableName:'Label',
						middleKey:'country_id',
						key:'id',
						searchItem:{
							status:1
						},
						condition:'=',
						info:['title']
					},
					town:{
						tableName:'Label',
						middleKey:'town_id',
						key:'id',
						searchItem:{
							status:1
						},
						condition:'=',
						info:['title']
					}
				};
				const callback = (res) => {
					if (res.solely_code==100000) {
						self.userData = res.info.data[0]
						self.submitData.name = self.userData.info.name;
						self.submitData.phone = self.userData.info.phone;
						self.submitData.gender = self.userData.info.gender;
						self.address = self.userData.city.title+self.userData.country.title+self.userData.town.title
						if(self.userData.info.name!=''){
							self.hasRegister = true
							
						}
					}else{
						self.$Utils.showToast(res.msg, 'none')
					}
					self.$Utils.finishFunc('getUserData');
				};
				self.$apis.userGet(postData, callback);
			},
			
			change(curr) {
				const self = this;
				if (curr != self.submitData.gender) {
					self.curr = curr
					self.submitData.gender = self.curr
				}
			},

			
			submit() {
				const self = this;
				uni.setStorageSync('canClick', false);
				var phone = self.submitData.phone;
				const pass = self.$Utils.checkComplete(self.submitData);
				console.log('pass', pass);
				console.log('self.submitData',self.submitData)
				if (pass) {
								
						const callback = (user, res) => {
							self.userInfoUpdate();
						};
						self.$Utils.getAuthSetting(callback);
						
					
				} else {
					uni.setStorageSync('canClick', true);
					self.$Utils.showToast('请补全信息', 'none')
				};
			},
					
			userInfoUpdate() {
				const self = this;
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				/* if(!wx.getStorageSync('user_info')||!wx.getStorageSync('user_info').headImgUrl){
				  postData.refreshToken = true;
				}; */
				postData.data = {};
				postData.data = self.$Utils.cloneForm(self.submitData);
				
				const callback = (data) => {				
					if (data.solely_code == 100000) {					
						self.$Utils.showToast('修改成功', 'none');
						setTimeout(function() {
							uni.navigateBack({
								delta:1
							})
						}, 800);
					} else {
						uni.setStorageSync('canClick', true);
						self.$Utils.showToast(data.msg, 'none', 1000)
					}	
				};
				self.$apis.userInfoUpdate(postData, callback);
			},

		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	@import "../../assets/style/personInfor.css";
</style>