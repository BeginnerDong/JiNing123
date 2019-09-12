<template>
	<!-- content部分 -->
	<view class="article_detail">
		<view @click="Router.navigateTo({route:{path:'/pages/articledetail/articledetail?id='+item.id}})" 
		:key="index" v-for="(item,index) in mainData" class="article_box">
			<view class="article_img">
				<image :src="item.mainImg[0].url"></image>
			</view>
			<view class="article_detail_box">
				<view class="article_detail_title avoidOverflow" v-html="item.title"></view>
				<view class="article_detail_main avoidOverflow2">{{item.description}}</view>
				<view class="article_detail_date">{{item.create_time}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				mainData:[]
			}
		},
		
		onLoad() {
			const self = this;
			self.paginate = self.$Utils.cloneForm(self.$AssetsConfig.paginate);
			self.$Utils.loadAll(['getMainData'], self);
		},
		
		onReachBottom() {
			console.log('onReachBottom')
			const self = this;
			if (!self.isLoadAll && uni.getStorageSync('loadAllArray')) {
				self.paginate.currentPage++;
				self.getMainData()
			};
		},
		
		methods: {

			
			
			getMainData() {
				const self = this;
				const postData = {};
				postData.paginate = self.$Utils.cloneForm(self.paginate);
				postData.searchItem = {
					thirdapp_id:2
				};
				postData.getBefore = {
					caseData: {
						tableName: 'Label',
						searchItem: {
							title: ['=', ['政策法规']],
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

		},
	};
</script>

<style scoped>
	/* content部分 */
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/news.css");
	page{padding-bottom: 60rpx;}

</style>
