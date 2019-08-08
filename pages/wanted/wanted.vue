<template>
	<view style="width:100%;height: 100%;">
		<!-- search部分 -->
		<view class="search flex flexCenter">
			<input class="searchword" type="text" placeholder="请输入关键词"/>
			<view class="searchIcon">
				<image src="../../static/images/question-icon1.png" style="width: 100%;height: 100%;"></image>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content flex lexCenter">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_complete">已完结</view>
				</view>
				<view style="width: 100%;height: 30rpx;"></view>
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
					<view style="width: 100%;height: 40rpx;"></view>
				</view>
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_noaccept">未受理</view>
				</view>
				<view style="width: 100%;height: 30rpx;"></view>
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
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_noaccept">未受理</view>
				</view>
				<view style="width: 100%;height: 30rpx;"></view>
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
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_noaccept">未受理</view>
				</view>
				<view style="width: 100%;height: 30rpx;"></view>
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
			</view>
		</view>
		<ask-question></ask-question>
	</view>
</template>

<script>
	import askQuestion from "@/components/askQuestion/askQuestion.vue"
	export default {
		components: {
			askQuestion
		},
		data() {
			return {
				Router:this.$Router
			}
		}
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* search部分 */
	.search{width: 100%;height: 100rpx;background: #E5E5E5;}
	.searchword{background:#ffffff;width: 690rpx;height: 60rpx;font-size: 24rpx;border: solid 1px #999999;text-indent: 20rpx;border-radius: 10rpx;position: relative;}
	.searchIcon{width: 30rpx;height: 30rpx;position: absolute;right: 8%;}
	/* content部分 */
	.content{flex-direction:column;padding-bottom: 98rpx;}
	.content_box{width: 690rpx;background: #FFFFFF;box-shadow: 0px 0px 6px #E5E5E5;}
	.content_box_question{display: flex;}
	.content_box_question_left{padding: 0 20rpx;float: left;height: 100%;}
	.content_box_question_left>image{width: 28rpx;height: 24rpx;}
	.content_box_question_right{float: left;font-size: 26rpx;}
	.response{color: #666666;font-size: 24rpx;}
	.lookdetail{font-size: 22rpx;color: #1095F9;text-align: right;}
	.info{justify-content: space-between;padding: 0 20rpx;}
	.my_name{font-size: 28rpx;color: #666666;margin-left: 20rpx;}
	.my_info_complete{font-size: 24rpx;color: #1095f9;}
	.my_info_noaccept{font-size: 24rpx;color: #ff3b3b;}
</style>
