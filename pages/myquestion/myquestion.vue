<template>
	<view>
		
		<view class="content flex flexCenter">
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view class="content_box_question">
					<image class="icon" src="../../static/images/question-icon2.png"></image>
					<view class="title">树木虫害问题</view>
					<view class="text overflow2">梁山县小安山镇青堌堆村村民反映，村东头种植的杨树上有许多长毛虫，掉落至村民身上产生刺痛感，希望相关部门尽快喷洒农药。</view>
				</view>
				<view class="lookdetail">
					查看详情
					<image src="../../static/images/particulars-icon2.png"></image>
				</view>
			</view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view class="content_box_question">
					<image class="icon" src="../../static/images/question-icon2.png"></image>
					<view class="title">2、道路交通设施</view>
					<view class="text overflow2">任城区刘先生反映，太白路樱花苑小区向西100米的小路口已设置礼让行人线，但未设置信号灯，仍存在安全隐患，建议在此处设置信号灯。</view>
				</view>
				<view class="lookdetail">
					查看详情
					<image src="../../static/images/particulars-icon2.png"></image>
				</view>
			</view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view class="content_box_question">
					<image class="icon" src="../../static/images/question-icon2.png"></image>
					<view class="title">3、道路积水</view>
					<view class="text overflow2">任城区火炬路和求贤路交叉口处，每逢下雨均出现道路积水现象，给行人车辆过往造成不便，希望相关部门尽快解决。</view>
				</view>
				<view class="lookdetail">
					查看详情
					<image src="../../static/images/particulars-icon2.png"></image>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	import cTabbar from "@/components/tabbar/tabbar.vue"
	
	export default {
		
		data() {
			return {
				Router:this.$Router
			}
		},
		methods: {
			
		},
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");

</style>
