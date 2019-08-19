<template>
	<view>
		<view class="container">
			<view class="list_item flex">
				<span class="sqr_common import">姓名:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入姓名">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">性别:</span>
				<radio-group class="radio-group" bindchange="radioChange">
					<label class="radio" >
						<radio value="男" checked=""/>男
					</label>
					<label class="radio" >
						<radio value="女" />女
					</label>
				</radio-group>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">联系电话:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入联系电话">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">验证码:</span>
				<view class="sqr_name phoneNum">
					<input type="text" placeholder="请输入验证码">
					<view class="yzm">获取验证码</view>
				</view>
			</view>
			<view>
				<button class="submitBtn" type="submit">提交</button>
			</view>
		</view>
	</view>
</template>

<script>

	export default {

		components: {
		
		},
		data() {
			return {
				Router:this.$Router
			};
		},
		methods: {
		
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	.import::before{content: "*"; color: red;margin-right: 6rpx; font-size: 28rpx;}
	.radio-group .radio{margin: 0 20rpx;}
	.phoneNum{display: flex; align-content: space-around; align-items: center; width: 70%;}
	.phoneNum input{width: 60%; text-align: left; }
	.yzm{ padding: 0 20rpx; color: #0066CC;font-size: 24rpx;background: #f5f5f5; width: 40%; text-align: center; height: 50rpx; line-height: 50rpx; box-sizing: border-box;}
	.submitBtn{ width: 80%;height: 80rpx;background: rgb(17, 149, 250);border-radius: 5px; line-height: 80rpx;color: #fff;text-align: center; margin: 80rpx auto;}
	
	.container{padding:0 30rpx;background: #ffffff;}
	.sqr_common{font-size: 28rpx;color: #222222;}
	.list_item{justify-content: space-between;padding: 40rpx 0;border-bottom: solid 1px #EAEAEA;align-items: flex-start;}
	.sqr_name{font-size: 24rpx;color: #999999;text-align: right;}
	.sqr_time{font-size: 28rpx;color: #222222;}
	textarea{width:536rpx;height:250rpx;font-size: 24rpx;color: #999999;background: #F5F5F5;text-align: left;padding-top:20rpx;text-indent: 10rpx;}
	.tabbar{width: 100%;height: 120rpx;background-color: white;border-top: solid 1px #EFEFEF;}
	.askquestion{width: 600rpx;height: 80rpx;background: #1195FA;border-radius: 10rpx;}
	.question{font-size: 28rpx;color: #FFFFFF;}
</style>