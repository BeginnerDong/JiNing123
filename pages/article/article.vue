<template>
	<!-- content部分 -->
	<view class="article_detail">
		<view @click="Router.navigateTo({route:{path:'/pages/articledetail/articledetail'}})" :key="index" v-for="(item,index) in article_list" class="article_box">
			<view class="article_img">
				<image src="../../static/images/article-icon.jpg"></image>
			</view>
			<view class="article_detail_box">
				<view class="article_detail_title avoidOverflow">济宁市公共交通集团有限公司党委书记、董事长马中阁接听政务热线</view>
				<view style="width: 100%;height: 30rpx;"></view>
				<view class="article_detail_main avoidOverflow2">7月31日，济宁市公共交通集团有限公司党委书记、董事长马中阁带领技术装备部、企业管理规划部、运营管理部、稽查管理部、安全管理部、客服管理部到市政务热线服务中心接听群众来话，现场受理有关接听城区公交线路设置、公交车班次间隔时间长等方面问题5件。</view>
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
				Router:this.$Router,
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
