<template>
	<view>
		<view class="pageBjH">
			<image class="bjImg" src="../../static/images/img3.png" mode=""></image>
			<view class="cont_BjH">
				<view class="contBox">
					
					<view class="hotlilneCont">
						<view class="content ql-editor"  v-html="mainData.content">
						</view>
					</view>
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
							title: ['=', ['使用帮助']],
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

<style>
	@import "../../assets/style/wxParse.css";
	@import "../../assets/style/pageBj.css";
	
</style>