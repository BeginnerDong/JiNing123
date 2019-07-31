<template>
	<view class="article_detail">
		<!-- header部分 -->
		<view class="header">
			<view class="articledetail_header">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="articledetail_header_title avoidOverflow2">标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题</view>
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="articledetail_header_date">2019-5-23</view>
				<view style="width: 100%;height: 30rpx;"></view>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_title">一、标题标题标题标题标题标题标题</view>
			<view class="content_main">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box1">
					内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容。
				</view>
				<view style="width: 100%;height: 50rpx;"></view>
				<view class="sectionone avoidOverflow3">1.内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="sectionone avoidOverflow3">1.内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="sectionone avoidOverflow3">1.内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="section_img">
					<image src="../../static/images/img1.png"></image>
				</view>
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
				webself:this
			}
		}
			
	};
</script>

<style scoped>
	.articledetail_header{border-bottom: solid 1px #EAEAEA;}
	.articledetail_header_title{font-size: 28rpx;color: #222222;padding: 0 30rpx;}
	.articledetail_header_date{text-align: right;padding: 0 30rpx;color: #999999;}
	.content{padding: 0 30rpx;}
	.content_title{font-weight: 800;font-size: 26rpx;color: #222222;}
	.content_box1{color: #666666;font-size: 24rpx;}
	.sectionone{color: #666666;font-size: 24rpx;}
	.section_img{text-align: center;}
	.section_img>image{width: 600rpx;height: 300rpx;}
</style>
