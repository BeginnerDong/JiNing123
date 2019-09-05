<template>
	<view style="width:100%">
		<!-- banner部分 -->
		<view class="banner">
			<swiper class="swiper-box" indicator-dots="indicatorDots" autoplay="autoplay" interval="interval" duration="duration" indicator-color="#d8d8d8" indicator-active-color="#ca1c1d">
				<block v-for="(item,index) in labelData" :key="index" >
					<swiper-item  class="swiper-item" @click="Router.navigateTo({route:{path:'/pages/articledetail/articledetail'}})">
						<image :src="item.mainImg" class="slide-image"/>
						<view class="title avoidOverflow">{{item.title}}</view>
					</swiper-item>
				</block> 
			</swiper>
		</view>
		<view class="scrollMsg">
			<image class="icon" src="../../static/images/home-icon1.png" mode=""></image>
			<view class="avoidOverflow">梁山县小安山镇青堌堆村村民反映，村东头种植的杨树上有许多长毛虫</view>
		</view>
		
		<!-- 菜单 -->
		<view class="inde-nav">
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/acceptancenotice/acceptancenotice'}})">
				<image class="icon" src="../../static/images/home-icon2.png"></image>
				<view class="title">诉求提交</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/myAppeal/myAppeal'}})">
				<image class="icon" src="../../static/images/home-icon3.png"></image>
				<view class="title">我的诉求</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/mine/mine'}})">
				<image class="icon" src="../../static/images/home-icon4.png"></image>
				<view class="title">个人中心</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/newsList/newsList'}})">
				<image class="icon" src="../../static/images/home-icon5.png"></image>
				<view class="title">新闻动态</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/policyList/policyList'}})">
				<image class="icon" src="../../static/images/home-icon6.png"></image>
				<view class="title">政策法规</view>
			</view>
			<view class="item"  @click="Router.navigateTo({route:{path:'/pages/question/question'}})">
				<image class="icon" src="../../static/images/home-icon7.png"></image>
				<view class="title">常见问题</view>
			</view>
		</view>

	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				Router:this.$Router,
				labelData:[
					{
						mainImg:"../../static/images/banner.png",
						title:"1.连续坚持迎战台风背后，她们架起一条畅通的道路"
					},
					{
						mainImg:"../../static/images/img1.jpg",
						title:"2.连续坚持迎战台风背后，她们架起一条畅通的道路"
					},
					{
						mainImg:"../../static/images/home-img.jpg",
						title:"3.连续坚持迎战台风背后，她们架起一条畅通的道路"
					}
				]
			}
		},
		
		onLoad() {
			const self = this;
			//self.$Utils.loadAll(['getMainData'], self);
		},
		
		methods: {
			
		},
	}
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	page{padding-bottom: 140rpx;}
	  /* banner部分 */
	.banner{height: 400rpx;} 
	.banner .swiper-box{height: 100%;}
	.banner .swiper-box .swiper-item{ position: relative;}
	.banner .swiper-box image{width: 100%;height: 100%;}
	.banner .swiper-box .title{position: absolute;bottom: 0;left: 0;width: 100%;padding: 0 180rpx 0 3%;box-sizing: border-box;height: 80rpx;line-height: 80rpx;background: rgba(0,0,0,0.5);color: #fff;font-size: 28rpx;}
	.banner .swiper-box .swiper-dots-horizontal{bottom: 50%;}
	
	.scrollMsg{line-height: 80rpx;padding: 0 3% 0 90rpx;position: relative;height: 80rpx;background: #f3faff;border-bottom: 2rpx solid #e7e7e7;font-size: 26rpx;color: #666;}
	.scrollMsg .icon{ width: 42rpx; height: 38rpx;position: absolute;top: 21rpx;left: 3%;}
	
	.inde-nav{display: flex;flex-wrap: wrap;}
	.inde-nav .item{width: 33.3%;padding:50rpx 0; text-align: center;border-right: 2rpx solid #e7e7e7;border-bottom:2rpx solid #e7e7e7 ;box-sizing: border-box;}
	.inde-nav .item .icon{width:70rpx; height: 70rpx; display: block;margin: 0 auto;}
	.inde-nav .item .title{font-size: 28rpx; margin-top: 20rpx;}
		
</style>
