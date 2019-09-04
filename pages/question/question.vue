<template>
	<view>
		<!-- search部分 -->
		<view class="search flex flexCenter" style="background: #f5f5f5;">
			<input class="searchword" type="text" placeholder="请输入关键词"/>
			<view class="searchIcon">
				<image src="../../static/images/search-icon1.png" style="width: 100%;height: 100%;"></image>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content flex flexCenter" style="background: #fff;">
			<view class="content_box" v-for="(item,index) in myQuestData" :key="index" @click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail'}})">
				<view class="content_box_question">
					<image class="icon" src="../../static/images/appeal-icon1.png"></image>
					<view class="title">{{item.title}}</view>
					<view class="text overflow2">{{item.text}}</view>
				</view>
				<view class="lookdetail">
					查看详情
					<image src="../../static/images/appeal-icon2.png"></image>
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
				Router:this.$Router,
				num:0,
				myQuestData:[
					{
						state:"已受理",
						title:"1、树木虫害问",
						text:"梁山县小安山镇青堌堆村村民反映，村东头种植的杨树上有许多长毛虫，掉落至村民身上产生刺痛感，希望相关部门尽快喷洒农药。"
					},
					{
						state:"已评价",
						title:"2、道路交通设施",
						text:"任城区刘先生反映，太白路樱花苑小区向西100米的小路口已设置礼让行人线，但未设置信号灯，仍存在安全隐患，建议在此处设置信号灯。"
					},
					{
						state:"未处理",
						title:"3、道路积水",
						text:"任城区火炬路和求贤路交叉口处，每逢下雨均出现道路积水现象，给行人车辆过往造成不便，希望相关部门尽快解决。"
					}
				]
			}
		},
		methods:{
		}
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");

</style>
