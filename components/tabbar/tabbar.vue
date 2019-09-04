<template>
	<view class="flex flexCenter tabbar" style="" >
		<view class="tabbar_item" @click="!color_one?Router.redirectTo({route:{path:'/pages/index/index'}}):''">
			<view class="nav_img flex flexCenter">
			   <image :src="src_one"></image>
			</view>
			<view class="nav_title" :style="color_one?'color:'+basic_blue:''">首页</view>
		</view>
		<view class="tabbar_item"  @click="!color_two?Router.redirectTo({route:{path:'/pages/handySevice/handySevice'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image :src="src_two"></image>
		    </view>
		    <view class="nav_title" :style="color_two?'color:'+basic_blue:''">便民服务</view>
		</view>
		<view class="tabbar_item"  @click="!color_three?Router.redirectTo({route:{path:'/pages/hotlineIntroduce/hotlineIntroduce'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image :src="src_three"></image>
		    </view>
		    <view class="nav_title" :style="color_three?'color:'+basic_blue:''">热线介绍</view>
		</view>
		<view class="tabbar_item"  @click="!color_four?Router.redirectTo({route:{path:'/pages/useHelp/useHelp'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image :src="src_four"></image>
		    </view>
		    <view class="nav_title" :style="color_four?'color:'+basic_blue:''">使用帮助</view>
		</view>
		
		<view class="tabbar_item" @click="!color_five?Router.redirectTo({route:{path:'/pages/inforRegister/inforRegister'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image :src="src_five"></image>
		    </view>
		    <view class="nav_title" :style="color_five?'color:'+basic_blue:''">注册信息</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			list: Array
		},
		
		data() {
			return {
				currIndex: 0,
				src_one:'6666',
				src_two:'',
				src_three:'',
				color_one:false,
				color_two:false,
				color_three:false,
				color_four:false,
				color_five:false,
				basic_blue:this.$AssetsConfig.basic_blue,
				Router:this.$Router
			};
		},
		
		mounted:function(){
			const self = this;
			// console.log('$AssetsConfig',this.$AssetsConfig)
			var route = getCurrentPages()[0].__route__;
			console.log('route',route)
			if(route=="pages/index/index"){
				self.src_one = '../../static/images/nabar1-a.png';
				self.color_one = true;
				self.src_two = '../../static/images/nabar2.png';
				self.color_two = false;
				self.src_three = '../../static/images/nabar3.png';
				self.color_three = false;
				self.src_four = '../../static/images/nabar4.png';
				self.color_four = false;
				self.src_five = '../../static/images/nabar5.png';
				self.color_five = false;
				console.log('src_one',self.src_one)
			}else if(route=="pages/handySevice/handySevice"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2-a.png';
				self.color_two = true;
				self.src_three = '../../static/images/nabar3.png';
				self.color_three = false;
				self.src_four = '../../static/images/nabar4.png';
				self.color_four = false;
				self.src_five = '../../static/images/nabar5.png';
				self.color_five = false;
			}else if(route=="pages/hotlineIntroduce/hotlineIntroduce"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2.png';
				self.color_two = false;
				self.src_three = '../../static/images/nabar3-a.png';
				self.color_three = true;
				self.src_four = '../../static/images/nabar4.png';
				self.color_four = false;
				self.src_five = '../../static/images/nabar5.png';
				self.color_five = false;
			}else if(route=="pages/useHelp/useHelp"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2.png';
				self.color_two = false;
				self.src_three = '../../static/images/nabar3.png';
				self.color_three = false;
				self.src_four = '../../static/images/nabar4-a.png';
				self.color_four = true;
				self.src_five = '../../static/images/nabar5.png';
				self.color_five = false;
			}else if(route=="pages/inforRegister/inforRegister"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2.png';
				self.color_two = false;
				self.src_three = '../../static/images/nabar3.png';
				self.color_three = false;
				self.src_four = '../../static/images/nabar4.png';
				self.color_four = false;
				self.src_five = '../../static/images/nabar5-a.png';
				self.color_five = true;
			}
			
		},
		
		methods: {
			intoPath(){
				const self = this;
				const sale_token = uni.getStorageSync('sale_token');
				if(sale_token){
					self.$Router.redirectTo({route:{path:'/pages/salesman/salesman'}});
				}else{
					self.$Router.redirectTo({route:{path:'/pages/login/login'}});
				};	
			}
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	.tabbar{
		width: 100%;
		height: 120rpx;
		position: fixed;
		bottom: 0;
		left: 0;
		background-color: white;
		border-top: solid 1px #EFEFEF;
	}
	.tabbar_item{
		width: 50%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	.nav_img{
		width:100%;
		margin-bottom: 8rpx;
		text-align: center;
		overflow: hidden;
	}
	.nav_img image {
		width: 48rpx;
		height: 48rpx;
	}
	.nav_title{
		width:100%;
		font-size: 24rpx;
		color: #999;
		text-align: center;
	}
</style>