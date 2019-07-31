<template>
	<view class="container">
		<view class="header">
			受理须知
		</view>
		<view class="content">
			<view class="main avoidOverflow4">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你。</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="title">1.标题标题标题标题标题标题标题</view>	
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="main avoidOverflow4">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你。</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="main avoidOverflow4">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你。</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="title">2.标题标题标题标题标题标图标</view>	
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="main avoidOverflow4">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你。</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="main avoidOverflow4">内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容，让你让你让你让你让你让你让你让你让你让你。</view>
		</view>
		<have-read></have-read>
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
				webself:this,
			}
		}
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	.container{height: 100%;}
	.header{text-align: center;padding: 40rpx 0 30rpx;font-size: 30rpx;color: #222222;}
	.content{font-size: 26rpx;color: #575757;padding:0 30rpx;height: 100%;}
</style>
