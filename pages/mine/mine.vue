<template>
	<view>
		<!-- header部分 -->
		<view class="header flex">
			<image class="my_icon" src="../../static/images/about-img.png" style="width: 140rpx;height: 140rpx;"></image>
		</view>
		<view class="my_name">快乐的人</view>
		<view class="my_list">
			<view class="box" :key="index" v-for="(item,index) in my_list" @click="goPage(item.my_key)">
				<view class="my_list_box flex">
					<view class="my_info flex" >
						<image style="width: 32rpx;height: 32rpx;" :src="item.my_src"></image>
						<span class="title">{{item.my_title}}</span>
					</view>
					<image class="my_icon" style="width: 10rpx;height: 20rpx;" src="../../static/images/about-icon5.png"></image>
				</view>
			</view>
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
				Router:this.$Router,
				my_list:[
					{
						"my_src":"../../static/images/about-icon2.png",
						"my_title":"个人信息",
						"my_key":"myattention2"
					},
					// {
					// 	"my_src":"../../static/images/about-icon2.png",
					// 	"my_title":"我的诉求",
					// 	"my_key":"myquestion"
					// },
					// {
					// 	"my_src":"../../static/images/about-icon3.png",
					// 	"my_title":"我的关注",
					// 	"my_key":"myattention"
					// },
					{
						"my_src":"../../static/images/about-icon3.png",
						"my_title":"产品反馈",
						"my_key":"mycomment"
					},
				]
			}
		},
		methods: {
			goPage(id) {
				if(id=="myattention2"){
					this.$Router.navigateTo({route:{path:'/pages/personInfor/personInfor'}});
				}else if(id=="myquestion"){
					this.$Router.navigateTo({route:{path:'/pages/myquestion/myquestion'}});
				}else if(id=="myattention"){
					this.$Router.navigateTo({route:{path:'/pages/myattention/myattention'}});
				}else{
					this.$Router.navigateTo({route:{path:'/pages/mycomment/mycomment'}});
				}
			}
		},
			
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	/* header部分 */
	.header{width: 100%;height: 264rpx;justify-content: center;align-items: flex-end;background: url(../../static/images/about-icon1.png);background-size: 100% 100%;}
	.header>image{width: 100%;height: 100%;}
	.my_name{text-align: center;font-size: 28rpx;color: #222222;}
	.my_list_box{padding: 40rpx 0;margin: 0 20rpx;justify-content: space-between;border-bottom: solid 1px #EAEAEA;}
	.title{margin-left: 20rpx;}
	.my_icon{justify-content: flex-end;}
</style>
