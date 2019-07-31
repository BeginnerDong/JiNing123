<template>
	<view>
		<!-- comment部分 -->
		<view class="comment">
			<view class="content flex">
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="info_box flex">
								<view class="info_left">
									<view class="my_name">快乐的猫</view>
									<view class="my_name my_time">2019.02.03</view>
								</view>
								<view class="info_left flex del">
									<image style="width: 20rpx;height: 28rpx;margin-right: 10rpx;" src="../../static/images/discuss-icon1.png"></image>
									删除
								</view>
							</view>
							<view class="content_box_question_right response avoidOverflow2">
								评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论
							</view>
							<view style="width: 100%;height: 30rpx;"></view>
							<view class="discuss flex">
								<view class="discuss_image">
									<image style="width:28rpx;height: 24rpx;" src="../../static/images/question-icon2.png"></image>
								</view>
								<view class="discuss_response avoidOverflow2">
									问题问题问题问题问题问题问题问题问题问题问题问题问题问题?
								</view>
							</view>
						</view>
					
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
				<view style="width: 100%;height: 10rpx;background: #EAEAEA;"></view>
			</view>
			<view class="content flex">
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="info_box flex">
								<view class="info_left">
									<view class="my_name">快乐的猫</view>
									<view class="my_name my_time">2019.02.03</view>
								</view>
								<view class="info_left flex del">
									<image style="width: 20rpx;height: 28rpx;margin-right: 10rpx;" src="../../static/images/discuss-icon1.png"></image>
									删除
								</view>
							</view>
							<view class="content_box_question_right response avoidOverflow2">
								评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论内容评论
							</view>
							<view style="width: 100%;height: 30rpx;"></view>
							<view class="discuss flex">
								<view class="discuss_image">
									<image style="width:28rpx;height: 24rpx;" src="../../static/images/question-icon2.png"></image>
								</view>
								<view class="discuss_response avoidOverflow2">
									问题问题问题问题问题问题问题问题问题问题问题问题问题问题?
								</view>
							</view>
						</view>
					
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
			</view>
		</view>
		
	</view>
	
	
</template>

<script>
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* comment部分 */
	.content{flex-direction:column;}
	.content_box{width: 690rpx;background: #FFFFFF;}
	.content_box_question{display: flex;}
	.response{color: #666666;font-size: 24rpx;}
	.info{align-items: flex-start;padding: 0 20rpx;}
	.my_name{font-size: 28rpx;color: #666666;line-height: 28rpx;}
	.my_time{margin: 30rpx 0 34rpx;}
	.info_box{justify-content: space-between;align-items: flex-start;}
	.del{color:#666666;font-size: 24rpx;}
	.discuss_image{margin-right: 30rpx;}
	.discuss{align-items: flex-start;background: #f1f1f1;padding: 28rpx;}
</style>
