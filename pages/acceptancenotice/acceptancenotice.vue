<template>
	<view class="container">
		<view class="header">
			{{mainData.title}}
		</view>
		<view class="content">
		
			<view class="content ql-editor"  v-html="mainData.content">
			</view>
			<view style="width: 100%;height: 30rpx;"></view>
			
			<view class="flex flexCenter fixdBtn" style="" >
				<view class="askquestion flex flexCenter" @click="Router.navigateTo({route:{path:'/pages/askingquestion/askingquestion'}})">
					<span class="question">我已阅读并同意，继续反映</span>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		components: {},
		data() {
			return {
				Router: this.$Router,
				mainData:{}
			};
		},
		onLoad(options) {
			const self = this;

			self.$Utils.loadAll(['getMainData'], self);
		},

		methods: {

			getMainData() {
				const self = this;
				const postData = {};
				postData.searchItem = {
					thirdapp_id: 2
				};
				postData.getBefore = {
					caseData: {
						tableName: 'Label',
						searchItem: {
							title: ['=', ['受理须知']],
						},
						middleKey: 'menu_id',
						key: 'id',
						condition: 'in',
					},
				};
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.mainData = res.info.data[0];
					}
					self.$Utils.finishFunc('getMainData');
				};
				self.$apis.articleGet(postData, callback);
			},


		}
	}
</script>

<style scoped>
	@import url("../../assets/style/public.css");
	.container{height: 100%;}
	.header{text-align: center;padding: 40rpx 0 30rpx;font-size: 30rpx;color: #222222;}
	.content{font-size: 26rpx;color: #575757;padding:0 30rpx;height: 100%; line-height: 44rpx;padding-bottom:180rpx;}
	.content .title{font-weight: bold;}
	
	.fixdBtn{width: 100%;height: 120rpx;position: fixed;bottom: 0;left: 0;background-color: white;border-top: solid 1px #EFEFEF;}
	.askquestion{width: 600rpx;height: 80rpx;background: #ca1c1d;border-radius: 10rpx;}
	.question{font-size: 28rpx;color: #FFFFFF;}
</style>
