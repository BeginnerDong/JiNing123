<template>
	<view>
		<!-- header部分 -->
		<view class="header">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="header_title avoidOverflow">树木虫害问题</view>
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
