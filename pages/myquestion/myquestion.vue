<template>
	<view>
		<!-- header部分 -->
		<view class="header flex flexCenter">
			<view class="header_switch flex">
				<view class="hasquestion">待解决</view>
				<view class="noquestion actived">已解决</view>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content flex flexCenter">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答...
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答...
						</view>
						<view style="width: 20rpx;float: left;"></view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答...
						</view>
						<view style="width: 20rpx;float: left;"></view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import cTabbar from "@/components/tabbar/tabbar.vue"
	
	export default {
		
		data() {
			return {
				Router:this.$Router
			}
		},
		methods: {
			
		},
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* header部分 */
	.header{width: 100%;height: 70rpx;padding: 20rpx 0;background: #f5f5f5;}
	.header_switch{width: 690rpx;background: #FFFFFF;height: 100%;border: solid 1px #EEEEEE;border-radius: 10rpx;}
	.header_switch>view{flex: 1;text-align: center;height: 100%;line-height: 70rpx;}
	.actived{background: #1095F9;color: #ffffff;}
	/* content部分 */
	.content{flex-direction:column;}
	.content_box{width: 690rpx;height:306rpx;background: #FFFFFF;box-shadow: 0px 0px 6px #E5E5E5;}
	.content_box_question{display: flex;}
	.content_box_question_left{padding: 0 20rpx;float: left;height: 100%;}
	.content_box_question_left>image{width: 28rpx;height: 24rpx;}
	.content_box_question_right{float: left;font-size: 26rpx;}
	.response{color: #666666;font-size: 24rpx;}
	.lookdetail{font-size: 22rpx;color: #1095F9;text-align: right;}
	.hasquestion{border-top-left-radius: 10rpx;border-bottom-left-radius: 10rpx;}
	.noquestion{border-top-right-radius: 10rpx;border-bottom-right-radius: 10rpx;}
</style>
