<template>
	<!-- content部分 -->
	<view class="article_detail">
		<view @click="webself.$Router.navigateTo({route:{path:'/pages/articledetail/articledetail'}})" :key="index" v-for="(item,index) in article_list" class="article_box">
			<view class="article_img">
				<image src="../../static/images/article-icon.png"></image>
			</view>
			<view class="article_detail_box">
				<view class="article_detail_title avoidOverflow">内容内容内容内容内容内容内容内容内容内容</view>
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="article_detail_main avoidOverflow2">详情详情详情情详情详情详情详情详情详情</view>
				<view class="article_detail_date">2019-5-23</view>
			</view>
		</view>
	</view>
</template>

<script>
	
	export default {
		components: {
			
		},
		data() {
			return {
				webself:this,
				article_list:[
					{},
					{},
					{},
					{},
					{},
					{},
					{},
					{},
				]
			}
		}
			
	};
</script>

<style scoped>
	/* content部分 */
	@import url("../../assets/style/public.css");
	.article_detail{background: #FFFFFF;}
	.article_img{width: 250rpx;height: 166rpx;float: left;margin-right: 20rpx;}
	.article_img>image{width: 100%;height: 100%;}
	.article_box{overflow: hidden;margin: 0 30rpx;border-bottom: solid 1px #EAEAEA;padding: 31rpx 0 30rpx;margin: 0 20rpx;}
	.article_detail_title{font-size: 26rpx;color: #222222;}
	.article_detail_main{font-size: 22rpx;color: #999999;margin-bottom: 10rpx;}
	.article_detail_date{font-size: 22rpx;color: #999999;}
</style>
