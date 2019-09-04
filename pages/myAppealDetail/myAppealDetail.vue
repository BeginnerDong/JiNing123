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
		</view>
		<view class="sq_response">
			<view class="sq_response_title"><span class="sq_response_titlebox titXian">政府回复</span></view>
			<view style="width: 100%;height: 20rpx;"></view>
			<view class="sq_response_content avoidOverflow3">药已下发到各村，对杨树进行喷洒，感谢来电人的关注。
			</view>
		</view>
		<view>
			<image src="../../static/images/details-img.png" style="width: 385rpx;height: 333rpx; display: block;margin:60rpx auto;" mode=""></image>
		</view>
		
		<view class="satisftion">
			<view class="tit titXian">满意度评价:</view>
			<view class="selLis">
				<view class="qst">办理结果是否满意</view>
				<view class="r-selt">
					<view class="selt">
						<image src="../../static/images/appeal-icon4.png" mode=""></image>是
					</view>
					<view class="selt">
						<image src="../../static/images/appeal-icon5.png" mode=""></image>否
					</view>
				</view>
			</view>
			<view class="selLis">
				<view class="qst">服务态度是否满意</view>
				<view class="r-selt">
					<view class="selt">
						<image src="../../static/images/appeal-icon4.png" mode=""></image>是
					</view>
					<view class="selt">
						<image src="../../static/images/appeal-icon5.png" mode=""></image>否
					</view>
				</view>
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
	@import url("../../assets/style/question.css");
	
</style>
