<template>
	<view style="width:100%;height: 100%;background: #F2F2F2;">
		<!-- nav部分 -->
		<view>
			<ul class="qustNav flex">
				<li><span class="nav_actived">咨询</span></li>
				<li><span>投诉</span></li>
				<li><span>建议</span></li>
				<li><span>求租</span></li>
				<li><span>表扬</span></li>
				<li><span>其他</span></li>
			</ul>
		</view>
		<!-- content部分 -->
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
			
			
			<!-- <view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答
						</view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答...
						</view>
						<view style="width: 20rpx;float: left;"></view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_box" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box_question">
					<view class="content_box_question_left">
						<view style="width: 20rpx;"></view>
						<image src="../../static/images/question-icon2.png"></image>
					</view>
					<view class="content_box_question_right">
						问题问题问题问题问题问题问题问题问题问题问题问题?
					</view>
					<view style="width: 20rpx;float: left;"></view>
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view>
					<view class="content_box_question">
						<view class="content_box_question_left">
							<view style="width: 20rpx;"></view>
							<image src="../../static/images/question-icon3.png"></image>
						</view>
						<view class="content_box_question_right response avoidOverflow2">
							回答回答回答回答回答回答回答回答回答回答回答回答回答...
						</view>
						<view style="width: 20rpx;float: left;"></view>
					</view>
					<view style="width: 100%;height: 30rpx;"></view>
					<view class="lookdetail">
						查看详情
						<image style="width: 16rpx;height: 10rpx;margin-right:20rpx;margin-left:8rpx;transform: rotate(270deg);" src="../../static/images/particulars-icon2.png"></image>
					</view>
				</view>
			</view>
		 -->
		</view>
		
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
			}
		}
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");
	page{background: #f5f5f5;}

</style>
