<template>
	<view class="container">
		<view class="header">
			受理须知
		</view>
		<view class="content">
			<view class="title">一、受理范围</view>	
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="main">1、对全市改革开放、经济建设和社会发展等方面的意见和建议。</view>
			<view class="main">2、对政府各部门工作职责、办事程序和政策规定的咨询、意见和建议。</view>
			<view class="main">3、对政府及政府工作人员的批评和意见。</view>
			<view class="main">4、社会生活中发生的属于政府及其部门单位解决的有关问题的意见和建议。</view>
			<view class="main">非济宁本地事项、民事纠纷、党群、行政终结事项、法院、检察院、部队、武警、边防事项不在本平台的受理范围内，建议向对口单位或部门反馈。</view>
			<view style="width: 100%;height: 30rpx;"></view>
			<view class="title">二、注意事项</view>
			<view class="main">1、请遵守国家各项法律、规定，信息中不发表含有侮辱、猥亵、色情、人身攻击和反政府言论。</view>
			<view class="main">2、为方便联系沟通，全面掌握来信情况，请如实填写相关信息，留下有效联系电话。</view>
			<view class="main">3、请按照一事一诉的原则，诉求内容力求简明扼要、事实清楚、诉求明确。同一问题或相同内容已转部门或单位处理过程中请不要重复来信。</view>
			<view class="main">4、请不要发送乱码和无关文字，不发送只有网站链接无任何文字说明的信息。严禁上传木马等病毒，一经发现将严肃查处。</view>
			<view class="main">5、如果不希望在网上公开诉求信息，可以在“公开意向”选项中选择“不公开”，个人信息需要保密的，可以在“是否保密”选项中选择“是”，我们将对您的个人资料采取保密措施。</view>
			<view class="main">内容涉及国家安全、公共安全、经济安全、社会稳定以及国家秘密、商业秘密、个人隐私的信件将不予公开。</view>
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
		components: {
			// haveRead
		},
		data() {
			return {
				Router:this.$Router
			}
		}
			
	};
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
