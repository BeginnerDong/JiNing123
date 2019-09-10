<template>
	<view>
		<!-- header部分 -->
		<view class="header">
			<view style="width: 100%;height: 40rpx;"></view>
			<view class="header_title avoidOverflow">{{mainData.title}}</view>
			
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="header_content avoidOverflow4">
				{{mainData.content}}
			</view>
			
			<view style="width: 100%;height: 30rpx;"></view>
		</view>
		<view class="sq_response">
			<view class="sq_response_title"><span class="sq_response_titlebox titXian">政府回复</span></view>
			<view style="width: 100%;height: 20rpx;"></view>
			<view class="sq_response_content avoidOverflow3" v-if="mainData.passage1!=''">
				{{mainData.passage1}}
			</view>
			<view v-if="mainData.passage1==''">
				<image src="../../static/images/details-img.png" style="width: 385rpx;height: 333rpx; display: block;margin:60rpx auto;" mode=""></image>
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

<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");
	
</style>
