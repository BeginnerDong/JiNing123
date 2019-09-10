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
					<view class="selt" style="justify-content: flex-end;" @click="change('2')">
						<image :src="submitData.gender==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>女
					</view>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">联系电话:</span>
				<view class="sqr_name">
					<input type="number" maxlength="11" placeholder="请输入联系电话" v-model="submitData.phone">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">验证码:</span>
				<view class="sqr_name phoneNum" style="display: flex; justify-content: space-between;">
					<input type="text" placeholder="请输入验证码" style="display: block; width:260rpx;margin: 0;">
					<view class="yzm">获取验证码</view>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">选择省县乡:</span>
				<view class="sqr_name"  @click="showTree()">
					<!-- <input type="text" placeholder="请选择"> -->
					{{address!=''?address:'请选择'}}
					
				</view>
			</view>
			<view>
				<button class="submitBtn" type="submit" open-type="getUserInfo"  @getuserinfo="Utils.stopMultiClick(submit)">提交</button>
			</view>
		</view>
		<tki-tree ref="tkitree" :range="siteData" rangeKey="title" confirmColor="#4e8af7"  @confirm="treeConfirm" @cancel="treeCancel"/>
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
				siteData:[],
				Router: this.$Router,
				Utils: this.$Utils,
				curr: 1,
				address:'',
				submitData:{
					name:'',
					phone:'',
					gender:'',
					level:'',
					city_id:'0',
					country_id:'0',
					town_id:'',
					area_id:'0'
				}
			};
		},

		onLoad() {
			const self = this;
			
			var res = self.$Token.getProjectToken(function() {
				self.$Utils.loadAll(['getSiteData'], self)
			});
			if (res) {
				self.$Utils.loadAll(['getSiteData'], self)
			};
		},

		methods: {
			// 确定回调事件
			treeConfirm(e){
				const self = this;
				console.log(e)
				if(e[0]){
					self.submitData.area_id = e[0].id;
					self.submitData.level =e[0].parents.length+1; 
					if(e[0].parents.length==0){
						self.submitData.city_id = e[0].id;
						self.address = e[0].title
					};
					if(e[0].parents.length==1){
						self.submitData.city_id = e[0].parents[0].id
						self.submitData.country_id = e[0].id;
						self.address = e[0].parents[0].title+e[0].title
					};
					if(e[0].parents.length==2){
						self.submitData.city_id = e[0].parents[0].id
						self.submitData.country_id = e[0].parents[1].id
						self.submitData.town_id = e[0].id;
						self.address = e[0].parents[0].title+e[0].parents[1].title+ e[0].title
					};
				}
			},
			// 取消回调事件
			treeCancel(e){
				console.log(e)
			},
			// 显示树形选择器
			showTree(){
				this.$refs.tkitree._show();
			},
			
			change(curr) {
				const self = this;
				if (curr != self.submitData.gender) {
					self.curr = curr
					self.submitData.gender = self.curr
				}
			},

			getSiteData() {
				const self = this;
				const postData = {};
				postData.searchItem = {
					thirdapp_id: 2,
					type: 2
				};
				postData.order = {
					listorder: 'desc'
				};
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.siteData.push.apply(self.siteData, res.info.data);
						self.$Utils.finishFunc('getSiteData');
					};
				};
				self.$apis.labelGet(postData, callback);
			},
			
			submit() {
				const self = this;
				uni.setStorageSync('canClick', false);
				var phone = self.submitData.phone;
				const pass = self.$Utils.checkComplete(self.submitData);
				console.log('pass', pass);
				console.log('self.submitData',self.submitData)
				if (pass) {
						if(self.submitData.area_id==0){
							uni.setStorageSync('canClick', true);
							self.$Utils.showToast('请选择省县乡', 'none')
							return
						}			
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
				postData.saveAfter = [{
					tableName: 'User',
					FuncName: 'update',
					data: {
						level:self.submitData.level,
						city_id:self.submitData.city_id,
						country_id:self.submitData.country_id,
						town_id:self.submitData.town_id,
						area_id:self.submitData.area_id
					},
					searchItem: {
						user_no: wx.getStorageSync('user_info').user_no
					}
				}];
				const callback = (data) => {				
					if (data.solely_code == 100000) {					
						self.$Utils.showToast('注册成功', 'none');
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
