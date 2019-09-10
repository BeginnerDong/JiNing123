<template>
	<view class="article_detail">
		<!-- header部分 -->
		<view class="header">
			<view class="articledetail_header">
				<view class="articledetail_header_title avoidOverflow2" v-html="mainData.title"></view>
				<view class="articledetail_header_date">{{mainData.create_time}}</view>
			</view>
		</view>
		<!-- content部分 -->
		<view class="article_detail_Cont">
			<view class="content ql-editor"  v-html="mainData.content">
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
				mainData:{}
			}
		},
		onLoad(options) {
			const self = this;
			self.id = options.id;
			self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			
			getMainData() {
				const self = this;
				console.log('852369')
				const postData = {};
				postData.searchItem = {
					id:self.id
				};
				const callback = (res) => {
					if (res.solely_code == 100000 && res.info.data[0]) {
						self.mainData = res.info.data[0];
					} else {
						self.$Utils.showToast(res.msg, 'none')
					};
					self.$Utils.finishFunc('getMainData');

				};
				self.$apis.articleGet(postData, callback);

			},

		},
	};
</script>

<style>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/news.css");
	page{padding-bottom: 80rpx;}
</style>
