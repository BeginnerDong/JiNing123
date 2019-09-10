<template>
	<view>
		<!-- search部分 -->
		<view class="search flex flexCenter" style="background: #f5f5f5;" @click="search()">
			<input class="searchword" type="text" placeholder="请输入关键词" v-model="title"/>
			<view class="searchIcon">
				<image src="../../static/images/search-icon1.png" style="width: 100%;height: 100%;"></image>
			</view>
		</view>
		<!-- content部分 -->
		<view class="content flex flexCenter" style="background: #fff;">
			<view class="content_box" v-for="(item,index) in mainData" :key="index" 
			@click="Router.navigateTo({route:{path:'/pages/questiondetail/questiondetail?id='+item.id}})">
				<view class="content_box_question">
					<image class="icon" src="../../static/images/appeal-icon1.png"></image>
					<view class="title">{{item.title}}</view>
					<view class="text overflow2">{{item.content}}</view>
				</view>
				<view class="lookdetail">
					查看详情
					<image src="../../static/images/appeal-icon2.png"></image>
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
				title:'',
				searchItem:{
					thirdapp_id:2
				}
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

			search(){
				const self = this;
				if(self.title==''){
					self.$Utils.showToast('搜索条件无效','none')
				}else{
					self.searchItem.title = self.title;
					self.getMainData(true)
				}
			},
			
			getMainData(isNew) {
				const self = this;
				if(isNew){
					self.$Utils.clearPageIndex(self)
				};
				const postData = {};
				postData.searchItem = self.$Utils.cloneForm(self.searchItem)
				postData.paginate = self.$Utils.cloneForm(self.paginate)
				postData.getBefore = {
					caseData: {
						tableName: 'Label',
						searchItem: {
							title: ['=', ['常见问题']],
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
				self.$apis.searchQusetion(postData, callback);
			},

		},
	};
</script>


<style scoped>
	@import url("../../assets/style/public.css");
	@import url("../../assets/style/question.css");

</style>
