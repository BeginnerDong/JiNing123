<template>
	<view>
		<view class="pageBjH">
			<image class="bjImg" :src="mainData.mainImg[0].url" mode=""></image>
			<view class="cont_BjH">
				<view class="contBox">
					<view class="handyCont">
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
		data() {
			return {
				Router:this.$Router,
				handyDate:[
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"},
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"},
					{name:"法律援助中心",phone:"12348"},
					{name:"公积金管理中心",phone:"12329"},
					{name:"市人社局电话咨询服务",phone:"12333"},
					{name:"公交服务热线",phone:"2350000"},
					{name:"济宁供电公司客服电话",phone:"8395598"},
					{name:"中山税务服务热线",phone:"2321111"}
				],
				
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
					thirdapp_id:2
				};
				postData.getBefore = {
					caseData: {
						tableName: 'Label',
						searchItem: {
							title: ['=', ['便民服务']],
						},
						middleKey: 'menu_id',
						key: 'id',
						condition: 'in',
					},
				};
				const callback = (res) => {
					if (res.info.data.length > 0) {
						self.mainData = res.info.data[0];
						const regex = new RegExp('<img', 'gi');
						self.mainData.content = self.mainData.content.replace(regex, `<img style="max-width: 100%;"`);
					}
					self.$Utils.finishFunc('getMainData');
				};
				self.$apis.articleGet(postData, callback);
			},
			
			
		}
	}
</script>

<style>
	@import "../../assets/style/pageBj.css";
	
</style>