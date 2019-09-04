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
				<view class="r-selt">
					<view class="selt" style="justify-content: flex-end;">
						<image src="../../static/images/appeal-icon4.png" mode=""></image>男
					</view>
					<view class="selt" style="justify-content: flex-end;">
						<image src="../../static/images/appeal-icon5.png" mode=""></image>女
					</view>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">联系电话:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入联系电话">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">验证码:</span>
				<view class="sqr_name phoneNum" style="display: flex; justify-content: space-between;">
					<input type="text" placeholder="请输入验证码" style="display: block; width:260rpx;margin: 0;">
					<view class="yzm">获取验证码</view>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common import">选择省县乡:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请选择">
				</view>
			</view>
			<view>
				<button class="submitBtn" type="submit">提交</button>
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
				Router:this.$Router
			};
		},
		methods: {
		
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	@import "../../assets/style/personInfor.css";
</style>