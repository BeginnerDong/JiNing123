<template>
	<view style="width:100%">
		<!-- banner部分 -->
		<view class="banner">
			<view class="banner_img">
				<image class="imgbanner" src="../../static/images/home-banner.jpg"></image>
			</view>
			<view class="banner_circle">
				<ul class="banner_circle_box">
					<li class="circle"></li>
					<li class="space"></li>
					<li class="circle current"></li>
					<li class="space"></li>
					<li class="circle"></li>
					<li class="space"></li>
					<li class="circle"></li>
				</ul>
			</view>
		</view>
		<!-- letter部分 -->
		<view class="letter">
			<view class="letter_space"></view>
			<view class="letter_top">
				<span class="bigTitle">为民务实、规范高效</span>
			</view>
			<view class="letter_main">
				<span class="middleTitle">应答民生诉求，服务百姓需要</span>
			</view>
			<view class="letter_bottom">
				<p class="avoidOverflow">内容内容内容内容内容内容内容内容内容内容内容内容</p>
				<p class="avoidOverflow">内容内容内容内容内容内容内容内容内容内容内容内容</p>
				<p class="avoidOverflow">内容内容内容内容内容内容内容内容内容内容内容内容</p>
			</view>
			<view class="letter_space"></view>
		</view>
		<view style="width: 100%;height: 10rpx;background: #F2F2F2;"></view>
		<!-- nav部分 -->
		<view class="nav">
			<view style="width: 100%;height: 60rpx;"></view>
			<view class="nav_top">
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/consult/consult'}})">
					<view class="nav_content_img">
						<image class="icon" src="../../static/images/home-icon1.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>咨询</span>
					</view>
				</view>
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/complaint/complaint'}})">
					<view class="nav_content_img">
						<image class="icon" style="width: 82rpx;height: 75rpx;" src="../../static/images/home-icon2.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>投诉</span>
					</view>
				</view>
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/advice/advice'}})">
					<view class="nav_content_img">
						<image class="icon" src="../../static/images/home-icon3.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>建议</span>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 60rpx;"></view>
			<view class="nav_top">
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/wanted/wanted'}})">
					<view class="nav_content_img">
						<image class="icon" src="../../static/images/home-icon4.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>求租</span>
					</view>
				</view>
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/praise/praise'}})">
					<view class="nav_content_img">
						<image class="icon" src="../../static/images/home-icon5.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>表扬</span>
					</view>
				</view>
				<view class="nav_content_box" @click="Router.navigateTo({route:{path:'/pages/rest/rest'}})">
					<view class="nav_content_img">
						<image class="icon" src="../../static/images/home-icon6.png"></image>
						<view style="width: 100%;height: 30rpx;"></view>
					</view>
					<view class="nav_content_title">
						<span>其他</span>
					</view>
				</view>
			</view>
			<view style="width: 100%;height: 60rpx;"></view>
			<!-- <view style="width: 100%;height: 60rpx;"></view> -->
		</view>
		<view style="width: 100%;height: 10rpx;background: #F2F2F2;"></view>
		<!-- bottom部分 -->
		<view class="sbottom">
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="text">
				<view>新闻动态</view>
				<view>政策法规</view>
			</view>
			<image style="width: 100%;height:300rpx;" @click="Router.navigateTo({route:{path:'/pages/article/article'}})" src="../../static/images/home-img.jpg"></image>
			<view style="width: 100%;height: 40rpx;"></view>
		</view>
		<c-tabbar></c-tabbar>
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
	  /* banner部分 */
		.banner_img{width: 100%;height: 380rpx;}
		.imgbanner{width: 100%;height: 100%;}
		.banner{position: relative;}
		.banner_circle{position: absolute;left: 45%;bottom: 20rpx;}
		.banner_circle_box>li{float:left;height: 8rpx;}
		.circle{width: 8rpx;height: 100%;background: #8E8E90;border-radius: 100%;}
		.current{background: #0E95F6;}
		.space{ width: 14rpx;height: 100%;}
		/* letter部分 */
		.letter{text-align: center;background: #ffffff;}
		.letter_space{width: 14rpx;height: 50rpx;}
		.bigTitle{font-family: PingFang-SC-Bold;font-size:30rpx;line-height:30rpx;color: #222222;}
		.letter_main{margin: 30rpx auto;}
		.middleTitle{font-family: PingFang-SC-Bold;font-size:26rpx;line-height:26rpx;color: ##4C4C4C;}
		.letter_bottom{width: 100%;}
		.letter_bottom>p{font-family: PingFang-SC-Bold;font-size:24rpx;line-height:32rpx;width:100%;color: #595959;}
		/* nav部分 */
		.nav{background: #FFFFFF;}
		.nav_content_box{width: 33.3%;text-align: center;float: left;}
		.nav_top{overflow: hidden;}
		.nav_content_title{font-family: PingFang-SC-Bold;font-size:28rpx;line-height:28rpx;color: #242424;}
		
		.nav_content_img .icon{ width:70rpx; height: 70rpx;}
		/* bottom部分 */
		.sbottom{background: #FFFFFF;padding-bottom: 89rpx; position: relative;}
		.sbottom .text{ position: absolute; top: 40rpx;left: 40rpx;color: #fff; z-index: 6; font-size: 34rpx; text-align: center;}
		.sbottom .text>view{line-height: 60rpx;}
		
		.bottomImg{}
		.home_bottom{width: 100%;height: 300rpx;}
</style>
