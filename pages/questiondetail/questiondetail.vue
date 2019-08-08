<template>
	<view style="width:100%;height: 100%;">
		<!-- header部分 -->
		<view class="header">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="header_title avoidOverflow">标题标题标题标题标题标题标题标题标题</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="header_content avoidOverflow4">
				内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你让你让你让你让你。
			</view>
			
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="flex attention">
				<image style="width: 32rpx;height: 28rpx;" src="../../static/images/about-icon3.png"></image>
				<span class="attention_box">关注</span>
			</view>
			<view style="width: 100%;height: 30rpx;"></view>
		</view>
		<view style="width: 100%;height: 10rpx;background: #F2F2F2;"></view>
		<view class="sq_response">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="sq_response_title"><span class="sq_response_titlebox">社区答复</span></view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="sq_response_content avoidOverflow3">
				回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答回答。
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
		</view>
		<view style="width: 100%;height: 10rpx;background: #F2F2F2;"></view>
		<!-- comment部分 -->
		<view class="comment">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="sq_response_title"><span class="sq_response_titlebox">评论</span></view>
			<view class="content flex">
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="my_name">快乐的猫</view>
							<view class="my_name my_time">2019.02.03</view>
							<view class="content_box_question_right response avoidOverflow2">
								回答回答回答回答回答回答回答回答回答回答回答回答回答...
							</view>
							
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="my_name">快乐的猫</view>
							<view class="my_name my_time">2019.02.03</view>
							<view class="content_box_question_right response avoidOverflow2">
								回答回答回答回答回答回答回答回答回答回答回答回答回答...
							</view>
							
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="my_name">快乐的猫</view>
							<view class="my_name my_time">2019.02.03</view>
							<view class="content_box_question_right response avoidOverflow2">
								回答回答回答回答回答回答回答回答回答回答回答回答回答...
							</view>
							
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
				<view class="content_box">
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="info flex">
						<view class="my_icon">
							<image style="width: 80rpx;height: 80rpx;margin-right: 20rpx;" src="../../static/images/particulars-img1.png"></image>
						</view>
						<view>
							<view class="my_name">快乐的猫</view>
							<view class="my_name my_time">2019.02.03</view>
							<view class="content_box_question_right response avoidOverflow2">
								回答回答回答回答回答回答回答回答回答回答回答回答回答...
							</view>
							
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
				</view>
				
			</view>
			<view class="lookmore flex flexCenter">
				<span class="loadmore">查看更多</span>
				<image style="width: 16rpx;height: 10rpx;margin-left: 10rpx;" src="../../static/images/particulars-icon2.png"></image>
			</view>
		</view>
		<view class="exchange flex">
			<view class="send">
				<input class="needword" type="text" placeholder="想说点什么" />
			</view>
			<view class="sendbtn">发送</view>
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
			}
		}
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* header部分 */
	.header{padding: 0 30rpx;}
	.header_title{font-size: 30rpx;color: #222222;}
	.header_content{font-size: 26rpx;color: #666666;}
	.attention{justify-content: flex-end;}
	.attention_box{margin-left: 10rpx;color: #666666;font-size: 26rpx;}
	/* sq_response社区答复部分 */
	.sq_response{padding: 0 30rpx;}
	.sq_response_titlebox{font-size: 30rpx;color: #222222;font-weight: 800;}
	.sq_response_content{font-size: 28rpx;color: #222222;}
	/* comment部分 */
	.comment{padding: 0 30rpx;padding-bottom: 98rpx;}
	.content{flex-direction:column;}
	.content_box{width: 690rpx;background: #FFFFFF;border-bottom: solid 1px #EAEAEA;}
	.content_box_question{display: flex;}
	.content_box_question_left{padding: 0 20rpx;float: left;height: 100%;}
	.content_box_question_left>image{width: 28rpx;height: 24rpx;}
	.content_box_question_right{float: left;font-size: 26rpx;}
	.response{color: #666666;font-size: 24rpx;}
	.lookdetail{font-size: 22rpx;color: #1095F9;text-align: right;}
	.info{align-items: flex-start;padding: 0 20rpx;}
	.my_name{font-size: 28rpx;color: #666666;line-height: 28rpx;}
	.my_time{margin: 30rpx 0 34rpx;}
	.my_info_complete{font-size: 24rpx;color: #1095f9;}
	.my_info_noaccept{font-size: 24rpx;color: #ff3b3b;}
	.lookmore{padding: 50rpx 0;}
	.loadmore{color: #1095F9;font-size: 22rpx;}
	
	.exchange{width:100%;height: 98rpx;background: #F5F5F5;position: fixed;bottom: 0;left: 0;}
	.send{width: 74%;background: #FFFFFF;margin-left: 30rpx;}
	.needword{padding: 10rpx 0;text-indent: 20rpx;}
	.sendbtn{flex: 1;text-align: center;color: #1095F9;font-size: 28rpx;}
</style>
