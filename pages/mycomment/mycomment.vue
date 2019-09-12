<template>
	<view>
		<view class="section">
			<textarea value placeholder="写出你的评价内容" v-model="submitData.content" placeholder-style="color:#999; font-size:28rpx;" />
			
			<button class="pjbtn" type="button" @click="Utils.stopMultiClick(messageAdd)">提交</button>
		</view>
		
		<view class="alertBox" v-if="!is_show">
			<view class="infor">
				<img class="close" @click="closeAlert" src="../../static/images/wrong-icon1.png" alt="">
				<view class="tit">欢迎对本小程序提出意见建议</view>
				<view class="btn" @click="closeAlert">确定</view>
			</view>
		</view>
	
	</view>
		
</template>

<script>
	export default {
		data() {
			return {
				is_show:false,
				Router:this.$Router,
				Utils:this.$Utils,
				submitData:{
					content:'',
					type:2
				}
			}
		},
		methods: {
			closeAlert(){
				const self=this;
				self.is_show=!self.is_show
			},
			
			
					
			messageAdd() {
				const self = this;
				uni.setStorageSync('canClick', false);
				if(self.submitData.content==''){
					uni.setStorageSync('canClick', true);
					self.$Utils.showToast('请填写评价内容');
					return
				}
				const postData = {};
			
				postData.tokenFuncName = 'getProjectToken';
				/* if(!wx.getStorageSync('user_info')||!wx.getStorageSync('user_info').headImgUrl){
				  postData.refreshToken = true;
				}; */
				postData.data = {};
				postData.data = self.$Utils.cloneForm(self.submitData);
				const callback = (data) => {				
					if (data.solely_code == 100000) {	
						uni.setStorageSync('canClick', true);
						self.$Utils.showToast('提交成功','none');
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
				self.$apis.messageAdd(postData, callback);
			},
		}
			
	};
</script>

<style>
	@import url("../../assets/style/public.css");
	.section{padding-top: 40rpx;}
	.section textarea{ width: 90%;height: 300rpx; background: #f5f5f5;padding: 20rpx;box-sizing: border-box; display: block; margin: 0 auto; font-size: 28rpx;border-radius: 8rpx;}
	.pjbtn{width:80%;height: 80rpx; line-height: 80rpx;text-align: center;background: #CA1C1D;color: #fff;margin: 160rpx auto 100rpx auto; font-size: 30rpx;}
	.alertBox{ position: fixed; top: 0;right: 0;bottom: 0;left: 0;background: rgba(0,0,0,0.4); z-index: 10;}
	.alertBox .infor{ width: 80%;padding:100rpx 60rpx;box-sizing: border-box;background: #fff;border-radius: 10rpx;position: fixed; top: 50%;left: 50%;transform: translate(-50%,-50%);text-align: center; z-index: 12;}
	.alertBox .infor .tit{ font-size: 28rpx; color: #333;line-height: 40rpx; margin-bottom: 100rpx;}
	.alertBox .infor .btn{ width: 200rpx;height: 60rpx;line-height: 60rpx; background: #CA1C1D; color: #fff;font-size: 30rpx;border-radius: 8rpx;margin: 0 auto;}
	.close{ position: absolute;top: 0rpx;right: 0rpx;padding: 20rpx; width: 40rpx;height: 40rpx;}
	
</style>
