<template>
	<view>
		<!-- header部分 -->
		<view class="header">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="header_title avoidOverflow">树木虫害问题</view>
			<view class="state ok">已受理</view>
			<view class="state ing" v-if="is_show">办理中</view>
			<view class="state rst" v-if="is_show">处理结果</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="header_content avoidOverflow4">梁山县小安山镇青堌堆村村民反映，村东头种植的杨树上有许多长毛虫，掉落至村民身上产生刺痛感，希望相关部门尽快喷洒农药。
			</view>
			
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="flex attention">
				<image style="width: 32rpx;height: 28rpx;" src="../../static/images/about-icon3.png"></image>
				<span class="attention_box">关注</span>
			</view>
			<view style="width: 100%;height: 30rpx;"></view>
		</view>
		<view class="sq_response">
			<view class="sq_response_title"><span class="sq_response_titlebox">梁山县政府回复</span></view>
			<view style="width: 100%;height: 20rpx;"></view>
			<view class="sq_response_content avoidOverflow3">药已下发到各村，对杨树进行喷洒，感谢来电人的关注。
			</view>
		</view>
		
		<view class="satisftion">
			<view class="tit">满意度评价:</view>
			<view class="selLis">
				<view class="qst">办理结果是否满意</view>
				<radio-group class="radio-group" bindchange="radioChange">
					<label class="radio" >
						<radio value="是" checked=""/>是
					</label>
					<label class="radio" >
						<radio value="否" />否
					</label>
				</radio-group>
			</view>
			<view class="selLis">
				<view class="qst">服务态度是否满意</view>
				<radio-group class="radio-group" bindchange="radioChange">
					<label class="radio" >
						<radio value="是" checked=""/>是
					</label>
					<label class="radio" >
						<radio value="否" />否
					</label>
				</radio-group>
			</view>
			<!-- 为否时显示 textarea-->
			<view class="section">
				<textarea value placeholder="写出你的评价内容" placeholder-style="color:#999; font-size:24rpx;" />
			</view>
			<view>
				<button class="pjbtn" type="button">评价</button>
			</view>
		</view>
		
		<!-- comment部分 -->
		
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
				Router:this.$Router,
				is_show:false
			}
		},
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	
	.satisftion{padding: 30rpx; margin-bottom: 120rpx;}
	.satisftion .tit{font-size: 30rpx; font-weight: bold;padding-bottom: 40rpx;}
	.satisftion .selLis{line-height: 44rpx;text-align: center;display: flex;justify-content: space-between; align-items: center; height: 100rpx;}
	.satisftion .qst{ line-height: 40rpx; font-size: 24rpx;}
	.satisftion .radio{margin:0 30rpx; font-size: 28rpx;}
	.section textarea{ width: 96%;height: 160rpx; background: #f5f5f5;padding: 20rpx;box-sizing: border-box; display: block; margin: 0 auto; font-size: 28rpx; margin-top: 20rpx;}
	.pjbtn{width:80%;height: 80rpx; line-height: 80rpx;text-align: center;background: rgb(17, 149, 250);color: #fff;margin: 80rpx; font-size: 28rpx;}
	
	/* header部分 */
	.header{padding: 0 30rpx;}
	.header_title{font-size: 30rpx;color: #222222; font-weight: bold; width: 85%;}
	.state{ position: absolute; top: 16px;right:0rpx; color: #fff;background: #0066CC; border-radius: 40rpx 0 0 40rpx;padding: 0 20rpx; line-height: 50rpx;font-size: 28rpx;}
	
	/* 已受理 -蓝色 */
	.state.ok{background-color: #0066CC;}
	
	/* 办理中 橙色 */
	.state.ing{background-color: orange;}
	
	/* 处理结果 */
	.state.rst{background-color: #31c731;}
	.header_content{font-size: 28rpx;color: #666666; line-height: 40rpx;}
	.attention{justify-content: flex-end;}
	.attention_box{margin-left: 10rpx;color: #666666;font-size: 26rpx;}
	/* sq_response社区答复部分 */
	.sq_response{padding: 30rpx;border-top:10rpx solid rgb(242, 242, 242) ;border-bottom:10rpx solid rgb(242, 242, 242) ;}
	.sq_response_titlebox{font-size: 30rpx;color: #222222;font-weight: 800;}
	.sq_response_content{font-size: 28rpx;color: #222222; line-height: 40rpx;}
	
	.exchange{width:100%;height: 98rpx;background: #F5F5F5;position: fixed;bottom: 0;left: 0;}
	.send{width: 74%;background: #FFFFFF;margin-left: 30rpx;}
	
	.send .needword{padding: 10rpx 20rpx;box-sizing: border-box; line-height: 40rpx;height: 50rpx;}
	
	.sendbtn{flex: 1;text-align: center;color: #1095F9;font-size: 28rpx;}
</style>
