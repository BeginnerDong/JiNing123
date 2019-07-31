<template>
	<view style="width:100%;height: 100%;background: #F2F2F2;">
		<!-- nav部分 -->
		<view>
			<ul class="nav flex">
				<li><span class="nav_actived">咨询</span></li>
				<li><span>投诉</span></li>
				<li><span>建议</span></li>
				<li><span>求租</span></li>
				<li><span>表扬</span></li>
				<li><span>其他</span></li>
			</ul>
		</view>
		<!-- content部分 -->
		<view class="content flex flexCenter">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="webself.$Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
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
							回答回答回答回答回答回答回答回答回答回答回答回答回答
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
			<view class="content_box" @click="webself.$Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
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
			<view class="content_box" @click="webself.$Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
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
		<c-tabbar></c-tabbar>
	</view>
</template>

<script>
	import cTabbar from "@/components/tabbar/tabbar.vue"
	
	export default {
		components: {
			cTabbar
		},
		data() {
			return {
				webself:this
			}
		}
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* nav部分 */
	.nav{font-size: 28rpx;width: 100%;background: #FFFFFF;border: solid 1px #EFEFEF;height: 100rpx;}
	.nav>li{-webkit-flex: 1;text-align: center;color: #666666;}
	.nav>li>span{padding: 18rpx 0;}
	.nav_actived{line-height: 100%;color: #1095f9;border-bottom: solid 6px #1095F9;}
	/* content部分 */
	.content{flex-direction:column;padding-bottom: 98rpx;}
	.content_box{width: 690rpx;height:306rpx;background: #FFFFFF;box-shadow: 0px 0px 6px #E5E5E5;}
	.content_box_question{display: flex;}
	.content_box_question_left{padding: 0 20rpx;float: left;height: 100%;}
	.content_box_question_left>image{width: 28rpx;height: 24rpx;}
	.content_box_question_right{float: left;font-size: 26rpx;}
	.response{color: #666666;font-size: 24rpx;}
	.lookdetail{font-size: 22rpx;color: #1095F9;text-align: right;}
</style>
