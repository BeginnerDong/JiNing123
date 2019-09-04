<template>
	<view class="flex flexCenter tabbar" style="" >
		<view class="askquestion flex flexCenter" @click="Router.navigateTo({route:{path:'/pages/askingquestion/askingquestion'}})">
			<span class="question">我已阅读并同意，继续反映</span>
		</view>
	</view>
</template>

<script>
	import cTabbar from "@/components/tabbar/tabbar.vue"
	export default {
		props: {
			list: Array
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
	
	.tabbar{width: 100%;height: 120rpx;position: fixed;bottom: 0;left: 0;background-color: white;border-top: solid 1px #EFEFEF;}
	.askquestion{width: 600rpx;height: 80rpx;background: #ca1c1d;border-radius: 10rpx;}
	.question{font-size: 28rpx;color: #FFFFFF;}
</style>