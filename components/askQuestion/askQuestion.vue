<template>
	<view class="flex flexCenter tabbar" style="" >
		<view class="askquestion flex flexCenter" @click="webself.$Router.navigateTo({route:{path:'/pages/acceptancenotice/acceptancenotice'}})">
			<span class="question">提问题</span>
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
				webself:this
			};
		},
		methods: {
		
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	
	.tabbar{width: 100%;height: 120rpx;position: fixed;bottom: 0;left: 0;background-color: white;border-top: solid 1px #EFEFEF;}
	.askquestion{width: 600rpx;height: 80rpx;background: #1195FA;border-radius: 10rpx;}
	.question{font-size: 28rpx;color: #FFFFFF;}
</style>