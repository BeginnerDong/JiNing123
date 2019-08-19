<template>
	<view style="width:100%;height: 100%;background: #F2F2F2;">
		<!-- search部分 -->
		<view class="search flex flexCenter">
			<input class="searchword" type="text" placeholder="请输入关键词"/>
			<view class="searchIcon">
				<image src="../../static/images/question-icon1.png" style="width: 100%;height: 100%;"></image>
			</view>
		</view>
		<!-- nav部分 -->
		<view>
			<ul class="nav flex">
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
			
		</view>
		<c-tabbar></c-tabbar>
	</view>
</template>

<script>
	import cTabbar from "@/components/tabbar/tabbar.vue";
	
	
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
	/* search部分 */
	.search{width: 100%;height: 100rpx;background: #f5f5f5;}
	.searchword{width: 690rpx;height: 60rpx;font-size: 24rpx;border: solid 1px #999999;text-indent: 20rpx;border-radius: 10rpx;position: relative;}
	.searchIcon{width: 30rpx;height: 30rpx;position: absolute;right: 8%;}
	/* nav部分 */
	.nav{font-size: 28rpx;width: 100%;background: #FFFFFF;border: solid 1px #EFEFEF;height: 100rpx;}
	.nav>li{-webkit-flex: 1;text-align: center;color: #666666;}
	.nav>li>span{padding: 16rpx 0;}
	.nav_actived{line-height: 100%;color: #1095f9;border-bottom: solid 6px #1095F9;}
	/* content部分 */
/* 	.content{flex-direction:column;padding-bottom: 98rpx;}
	.content_box{width: 94%;height:306rpx;background: #FFFFFF;box-shadow: 0px 0px 12rpx rgba(0,0,0,0.1); border-radius: 10rpx; padding-right: 10rpx; box-sizing: border-box; margin:10rpx auto;}
	.content_box_question{display: flex;}
	.content_box_question_left{padding: 0 20rpx;float: left;height: 100%;}
	.content_box_question_left>image{width: 28rpx;height: 24rpx;}
	.content_box_question_right{float: left;font-size: 26rpx;}
	.response{color: #666666;font-size: 24rpx;}
	.lookdetail{font-size: 22rpx;color: #1095F9;text-align: right;} */
</style>
