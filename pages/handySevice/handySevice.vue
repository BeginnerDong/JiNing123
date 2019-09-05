<template>
	<view>
		<view class="pageBjH">
			<image class="bjImg" src="../../static/images/img1.png" mode=""></image>
			<view class="cont_BjH">
				<view class="contBox">
					<view class="handyCont">
						<view class="item" v-for="(item,index) in handyDate" :key="index">
							<view class="name">{{item.name}}</view>
							<view class="phone">{{item.phone}}</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>

	export default {
		data() {
			return {
				Router:this.$Router,
				handyDate:[
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"},
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"},
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"}
				]
			};
		},
		methods: {
		
		}
	}
</script>

<style>
	@import "../../assets/style/pageBj.css";
	
</style>