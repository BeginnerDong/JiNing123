<template>
	<view style="width:100%;height: 100%;">
		<!-- search部分 -->
		<view class="search flex flexCenter">
			<input class="searchword" type="text" placeholder="请输入关键词"/>
			<view class="searchIcon">
				<image src="../../static/images/question-icon1.png" style="width: 100%;height: 100%;"></image>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content flex lexCenter">
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_complete">已完结</view>
				</view>
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
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_complete">已完结</view>
				</view>
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
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_complete">已完结</view>
				</view>
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
				<view class="info flex">
					<view class="my_icon flex">
						<image style="width: 80rpx;height: 80rpx;" src="../../static/images/particulars-img1.png"></image>
						<span class="my_name">快乐的猫</span>
					</view>
					<view class="my_info_complete">已完结</view>
				</view>
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
			
		</view>
		<ask-question></ask-question>
	</view>
</template>

<script>
	import askQuestion from "@/components/askQuestion/askQuestion.vue"
	export default {
		components: {
			askQuestion
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
	@import url("../../assets/style/question.css");
	.info{justify-content: space-between;padding-bottom: 20rpx;}
	page{padding-bottom: 160rpx;background: #f5f5f5;}
	
</style>
