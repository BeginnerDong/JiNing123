<template>
	<view style="width:100%">
		<!-- banner部分 -->
		<view class="banner">
			<swiper class="swiper-box" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" indicator-color="#d8d8d8" indicator-active-color="#ca1c1d">
				<block v-for="(item,index) in mainData" :key="index" >
					<swiper-item  class="swiper-item" 
					@click="Router.navigateTo({route:{path:'/pages/articledetail/articledetail?id='+item.id}})">
						<image :src="item.mainImg[0].url" class="slide-image"/>
						<view style="display: flex;" class="title avoidOverflow">
							<view style="width: 79%;overflow: hidden;padding: 0 10px;">
								<view v-html="item.title"></view>
							</view>
							<view style="display: inline-block;width: 21%;">. . . . . .</view>
						</view>
						
					</swiper-item>
				</block> 
			</swiper>
		</view>
		<view class="scrollMsg">
			<image class="icon" src="../../static/images/home-icon1.png" mode=""></image>
			<uni-notice-bar 
			    show-icon="false" 
			    scrollable="true" single="true" color="#999"
			    :text="labelData.description">
			</uni-notice-bar>
		</view>
		
		<!-- 菜单 -->
		<view class="inde-nav">
			<view class="item flexCenter" @click="Router.navigateTo({route:{path:'/pages/acceptancenotice/acceptancenotice'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon2.png"></image>
					<view class="title">诉求提交</view>
				</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/myAppeal/myAppeal'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon3.png"></image>
					<view class="title">我的诉求</view>
				</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/mine/mine'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon4.png"></image>
					<view class="title">个人中心</view>
				</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/newsList/newsList'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon5.png"></image>
					<view class="title">新闻动态</view>
				</view>
			</view>
			<view class="item" @click="Router.navigateTo({route:{path:'/pages/policyList/policyList'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon6.png"></image>
					<view class="title">政策法规</view>
				</view>
			</view>
			<view class="item"  @click="Router.navigateTo({route:{path:'/pages/question/question'}})">
				<view class="cont">
					<image class="icon" src="../../static/images/home-icon7.png"></image>
					<view class="title">常见问题</view>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	import uniNoticeBar from "@/components/uni-notice-bar/uni-notice-bar"
	export default {
		components: {
			uniNoticeBar	
		},
		data(){
			return {
				mainData:[],
				Router:this.$Router,
				indicatorDots: false,
				autoplay: true,
				interval: 2000,
				duration: 500,
				labelData:{}
			}
		},
		
		onLoad() {
			const self = this;
			console.log(self.$Utils.formatTime())
			self.$Utils.loadAll(['getMainData','getLabelData'], self);
		},
		
		methods: {
			getMainData() {
				const self = this;
				const postData = {};
			
				postData.searchItem = {
					thirdapp_id:2
				};
				postData.getBefore = {
					caseData: {
						tableName: 'Label',
						searchItem: {
							title: ['=', ['首页轮播']],
						},
						middleKey: 'menu_id',
						key: 'id',
						condition: 'in',
					},
				};
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.mainData.push.apply(self.mainData, res.info.data);
					}
					self.$Utils.finishFunc('getMainData');
				};
				self.$apis.articleGet(postData, callback);
			},
			
			getLabelData() {
				const self = this;
				const postData = {};
			
				postData.searchItem = {
					thirdapp_id:2,
					title:'首页广告'
				};
	
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.labelData = res.info.data[0]
					}
					self.$Utils.finishFunc('getLabelData');
				};
				self.$apis.labelGet(postData, callback);
			},
		},
	}
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	  /* banner部分 */
	.banner{height: 400rpx;} 
	.banner .swiper-box{height: 100%;}
	.banner .swiper-box .swiper-item{ position: relative;}
	.banner .swiper-box image{width: 100%;height: 100%;}
	.banner .swiper-box .title{position: absolute;bottom: 0;left: 0;width: 100%;box-sizing: border-box;height: 80rpx;line-height: 80rpx;background: rgba(0,0,0,0.5);color: #fff;font-size: 28rpx;}
	.banner .swiper-box .swiper-dots-horizontal{bottom: 50%;}
	
	.scrollMsg{line-height: 80rpx;padding: 0 3% 0 90rpx;position: relative;height: 80rpx;background: #f3faff;border-bottom: 2rpx solid #e7e7e7;font-size: 26rpx;color: #666; position: relative;z-index: 2;}
	.scrollMsg .icon{ width: 42rpx; height: 38rpx;position: absolute;top: 21rpx;left: 3%;}
	
	.inde-nav{display: flex;flex-wrap: wrap; position: fixed;bottom: 0;top: 485rpx; left: 0;right: 0;width: 100%;box-sizing: border-box;}
	.inde-nav .item{width: 33.3%;/* padding:94rpx 0; */ text-align: center;border-right: 2rpx solid #e7e7e7;border-bottom:2rpx solid #e7e7e7 ;box-sizing: border-box; height: 50%; display: flex;justify-content: center;align-items: center;}
	.inde-nav .item .icon{width:80rpx; height: 80rpx; display: block;margin: 0 auto;}
	.inde-nav .item .title{font-size: 28rpx; margin-top: 26rpx;}
		
</style>
