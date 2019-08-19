<template>
	<view class="section">
		<textarea value placeholder="写出你的评价内容" placeholder-style="color:#999; font-size:24rpx;" />
		
		<button class="pjbtn" type="button">提交</button>
	</view>
		
		
</template>

<script>
	import haveRead from "@/components/haveread/haveread.vue"
	export default {
		components: {
			haveRead
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
	.section{padding-top: 80rpx;}
	.section textarea{ width: 90%;height: 160rpx; background: #f5f5f5;padding: 20rpx;box-sizing: border-box; display: block; margin: 0 auto; font-size: 28rpx;}
	.pjbtn{width:80%;height: 80rpx; line-height: 80rpx;text-align: center;background: rgb(17, 149, 250);color: #fff;margin: 80rpx; font-size: 28rpx;}
</style>
