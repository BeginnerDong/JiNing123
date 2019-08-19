<template>
	<view class="article_detail">
		<!-- header部分 -->
		<view class="header">
			<view class="articledetail_header">
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="articledetail_header_title avoidOverflow2">济宁市公共交通集团有限公司党委书记、董事长马中阁接听政务热线</view>
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="articledetail_header_date">2019-5-23</view>
				<view style="width: 100%;height: 30rpx;"></view>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="content_title">一、济宁市公共交通集团有限公司党委书记、董事长马中阁接听政务热线</view>
			<view class="content_main">
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="content_box1">7月31日，济宁市公共交通集团有限公司党委书记、董事长马中阁带领技术装备部、企业管理规划部、运营管理部、稽查管理部、安全管理部、客服管理部到市政务热线服务中心接听群众来话，现场受理有关接听城区公交线路设置、公交车班次间隔时间长等方面问题5件。
				</view>
				<view style="width: 100%;height: 40rpx;"></view>
				<view class="section_img">
					<image src="../../static/images/newpic.png"></image>
				</view>
				<view class="section_img">
					<image src="../../static/images/newpic2.png"></image>
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
				Router:this.$Router
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
	.section_img>image{width: 100%;height: 480rpx;}
</style>
