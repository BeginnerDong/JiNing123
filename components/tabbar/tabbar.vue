<template>
	<view class="flex flexCenter tabbar" style="" >
		<view class="tabbar_item" @click="!color_one?Router.redirectTo({route:{path:'/pages/index/index'}}):''">
			<view class="nav_img flex flexCenter">
				
			   <image style="width: 43rpx;height: 43rpx;" :src="src_one"></image>
			</view>
			<view class="nav_title" :style="color_one?'color:'+basic_blue:''">首页</view>
		</view>
	   
		<view class="tabbar_item"  @click="!color_two?Router.redirectTo({route:{path:'/pages/question/question'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image style="width: 43rpx;height: 43rpx;" :src="src_two"></image>
		    </view>
		    <view class="nav_title" :style="color_two?'color:'+basic_blue:''">常见问题</view>
		</view>
		<view class="tabbar_item" @click="!color_three?Router.redirectTo({route:{path:'/pages/mine/mine'}}):''">
		    <view class="nav_img flex flexCenter">
			   <image style="width: 43rpx;height: 43rpx;" :src="src_three"></image>
		    </view>
		    <view class="nav_title" :style="color_three?'color:'+basic_blue:''">我的</view>
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
				console.log('src_one',self.src_one)
			}else if(route=="pages/question/question"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2-a.png';
				self.color_two = true;
				self.src_three = '../../static/images/nabar3.png';
				self.color_three = false;
			}else if(route=="pages/mine/mine"){
				self.src_one = '../../static/images/nabar1.png';
				self.color_one = false;
				self.src_two = '../../static/images/nabar2.png';
				self.color_two = false;
				self.src_three = '../../static/images/nabar3-a.png';
				self.color_three = true;
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
	}
	.nav_img{
		width:100%;
		height: 80rpx;
		text-align: center;
		overflow: hidden;
	}
	.nav_img image {
		width: 70rpx;
		height: 63rpx;
	}
	.nav_title{
		width:100%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 30rpx;
		text-align: center;
	}
</style>