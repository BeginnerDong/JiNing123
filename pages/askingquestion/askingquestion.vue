<template>
	<view>
		<view class="container">
			<view class="list_item flex">
				<span class="sqr_common">诉求人:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入诉求人姓名">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">来电时间:</span>
				<view class="sqr_time">
					2019/7/23 6:30:09
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">诉求人:</span>
				<view class="sqr_time flex">
					2019/7/23 6:30:09
					<image style="width: 20rpx;height: 13rpx;margin-left: 10rpx;" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">我的位置:</span>
				<view class="sqr_name flex">
					请选择
					<image style="width: 20rpx;height: 13rpx;margin-left: 10rpx;" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">问题标题:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入问题标题">
				</view>
			</view>
			<view class="list_item flex">
				<view class="contact_area">
					<span class="sqr_common">反应内容:</span>
				</view>
				<view class="sqr_name">
					<textarea value="" placeholder="请输入问题标题" />
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">诉求目的:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入诉求目的">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">类型:</span>
				<view class="sqr_name flex">
					请选择
					<image style="width: 20rpx;height: 13rpx;margin-left: 10rpx;" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">视频上传:</span>
				<view class="sqr_video">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;" src="../../static/images/askquestions-icon2.png"></image>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">文档上传:</span>
				<view class="sqr_video">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;" src="../../static/images/askquestions-icon3.png"></image>
				</view>
			</view>
			<view class="tabbar flex flexCenter" style="" >
				<view class="askquestion flex flexCenter" @click="">
					<span class="question">提交</span>
				</view>
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