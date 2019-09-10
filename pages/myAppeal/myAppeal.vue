<template>
	<view>
		<!-- content部分 -->
		<view class="content flex flexCenter">
			<view class="content_box" v-for="(item,index) in mainData" :key="index" 
			@click="Router.navigateTo({route:{path:'/pages/myAppealDetail/myAppealDetail?id='+item.id}})">
				<view class="state" v-if="item.deal_status==0">未处理</view>
				<view class="state" v-if="item.deal_status==1">已处理</view>
				<view class="state" v-if="item.deal_status==2">已评价</view>
				<view class="content_box_question">
					<image class="icon" src="../../static/images/appeal-icon1.png"></image>
					<view class="title">{{item.title}}</view>
					<view class="text overflow2">{{item.content}}</view>
				</view>
				<view class="lookdetail">
					查看详情<image src="../../static/images/appeal-icon2.png"></image>
				</view>
			</view>
			
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				mainData:[],
				
			}
		},
		
		onLoad() {
			const self = this;
			self.paginate = self.$Utils.cloneForm(self.$AssetsConfig.paginate);
		
		},
		
		onShow() {
			const self = this;
			self.mainData = [];
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

		
			
			getMainData(isNew) {
				const self = this;
				if(isNew){
					self.$Utils.clearPageIndex(self)
				};
				const postData = {
					tokenFuncName:'getProjectToken',
					searchItem:{
						type:1
					}
				};		
				postData.paginate = self.$Utils.cloneForm(self.paginate)
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.mainData.push.apply(self.mainData, res.info.data);
					}
					self.$Utils.finishFunc('getMainData');
				};
				self.$apis.messageGet(postData, callback);
			},

		},
	};
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");
	

</style>
