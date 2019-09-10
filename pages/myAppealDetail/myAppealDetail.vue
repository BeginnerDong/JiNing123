<template>
	<view >
		<!-- header部分 -->
		<view class="header">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="header_title avoidOverflow">{{mainData.title}}</view>
			<view class="state ok" v-if="mainData.deal_status==0">未处理</view>
			<view class="state ok" v-if="mainData.deal_status==1">已处理</view>
			<view class="state ok" v-if="mainData.deal_status==2">已评价</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="header_content avoidOverflow4">
				{{mainData.content}}
			</view>
			
			<view style="width: 100%;height: 30rpx;"></view>
		</view>
		<view class="sq_response">
			<view class="sq_response_title"><span class="sq_response_titlebox titXian">政府回复</span></view>
			<view style="width: 100%;height: 20rpx;"></view>
			<view class="sq_response_content avoidOverflow3" v-if="mainData.passage1!=''">
				{{mainData.passage1}}
			</view>
			<view v-if="mainData.passage1==''">
				<image src="../../static/images/details-img.png" style="width: 385rpx;height: 333rpx; display: block;margin:60rpx auto;" mode=""></image>
			</view>
		</view>
		
		
	
			<view class="satisftion" v-if="mainData&&mainData.passage1&&mainData.passage1!=''">
				<view class="tit titXian">满意度评价:</view>
				<view class="selLis">
					<view class="qst">办理结果是否满意</view>
					<view class="r-selt">
						<view class="selt" @click="mainData.deal_status!=2?change('1'):''">
							<image :src="submitData.result==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>是
						</view>
						<view class="selt" @click="mainData.deal_status!=2?change('2'):''">
							<image :src="submitData.result==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>否
						</view>
					</view>
				</view>
				<view class="selLis">
					<view class="qst">服务态度是否满意</view>
					<view class="r-selt">
						<view class="selt" @click="mainData.deal_status!=2?secrecy('1'):''">
							<image :src="submitData.service==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'"  mode=""></image>是
						</view>
						<view class="selt"   @click="mainData.deal_status!=2?secrecy('2'):''">
							<image :src="submitData.service==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>否
						</view>
					</view>
				</view>
				<!-- 为否时显示 textarea-->
				
				<view class="section" v-if="submitData.result==2||submitData.service==2">
					<textarea  :disabled="mainData.deal_status==2?true:false" placeholder="写出你的评价内容" placeholder-style="color:#999; font-size:24rpx;" v-model="submitData.passage2"/>
				</view>
				<view v-if="mainData.deal_status!=2">
					<button class="pjbtn" type="button" @click="Utils.stopMultiClick(messageUpdate)">评价</button>
				</view>
			</view>
		
		<!-- comment部分 -->
		
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		data() {
			return {
				Router:this.$Router,
				Utils:this.$Utils,
				mainData:{},
			
				submitData:{
					result:1,
					service:1,
					passage2:'',
					deal_status:2
				}
			}
		},
		
		onLoad(options) {
			const self = this;
			self.id = options.id;
			self.$Utils.loadAll(['getMainData'], self);
		},
		
		methods:{
			
			getMainData() {
				const self = this;
				console.log('852369')
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				postData.searchItem = {
					id:self.id
				};
				const callback = (res) => {
					if (res.solely_code == 100000 && res.info.data[0]) {
						self.mainData = res.info.data[0];
						self.submitData.passage2 = self.mainData.passage2
						self.submitData.result = self.mainData.result
						self.submitData.service = self.mainData.service
					} else {
						self.$Utils.showToast(res.msg, 'none')
					};
					self.$Utils.finishFunc('getMainData');
			
				};
				self.$apis.messageGet(postData, callback);
			
			},
			
			
					
			messageUpdate() {
				const self = this;
				uni.setStorageSync('canClick', false);
				if(self.submitData.result==2||self.submitData.service==2){
					if(self.submitData.passage2==''){
						uni.setStorageSync('canClick', true);
						self.$Utils.showToast('请填写评价内容');
						return
					}
				}
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				/* if(!wx.getStorageSync('user_info')||!wx.getStorageSync('user_info').headImgUrl){
				  postData.refreshToken = true;
				}; */
				postData.data = {};
				postData.data = self.$Utils.cloneForm(self.submitData);
				postData.searchItem = {
					id:self.id
				};
				const callback = (data) => {				
					if (data.solely_code == 100000) {	
						uni.setStorageSync('canClick', true);
						self.$Utils.showToast('评价成功','none');
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
				self.$apis.messageUpdate(postData, callback);
			},
			
			change(curr){
				const self=this
				if(curr!=self.submitData.result){
					self.submitData.result = curr
				}
			},
			
			secrecy(index){
				const self=this
				if(index!=self.submitData.service){
					self.submitData.service = index
				}
			},
		}
			
	};
</script>

<style scoped>
	
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");
	
</style>
