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
					<view class="selt" style="justify-content: flex-end;" @click="change('1')">
						<image :src="curr==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>男
					</view>
					<view class="selt" style="justify-content: flex-end;"  @click="change('2')">
						<image :src="curr==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>女
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
	
	</view>
</template>

<script>

	export default {
		data() {
			return {
				Router:this.$Router,
				curr:1
			};
		},
		methods: {
			change(curr){
				const self=this;
				if(curr!=self.curr){
					self.curr=curr
				}
			}
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	@import "../../assets/style/personInfor.css";
</style>