<template>
	<view>
		<view class="container">
			<view class="list_item flex">
				<view class="sqr_common">诉求人:</view>
				<view class="rr sqr_name">
					<input type="text" placeholder="请输入诉求人姓名">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">来电时间:</span>
				<view class="rr sqr_time">
					<input type="date" value="2019-09-14 14:30:09">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">时间:</span>
				<view class="rr sqr_time flex">
					<input type="date" value="2019-09-14 14:30:09">
					<image class="arrow" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">事发地址:</span>
				<view class="rr sqr_name flex">
					请选择
					<image class="arrow" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">问题标题:</span>
				<view class="rr sqr_name">
					<input type="text" placeholder="请输入问题标题">
				</view>
			</view>
			<view class="list_item flex">
				<view class="contact_area">
					<span class="sqr_common">反应内容:</span>
				</view>
				<view class="sqr_name">
					<textarea value="" placeholder="请输入问题标题" />
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">诉求目的:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入诉求目的">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">类型:</span>
				<view class="sqr_name flex">
					<view class="uni-list">
						<view class="uni-list-cell">
							<view class="uni-list-cell-db">
								<picker @change="bindPickerChange" :value="index" :range="array">
									<view class="uni-input">{{array[index]}}</view>
								</picker>
							</view>
						</view>
					</view>
					<!-- 请选择 -->
					<image class="arrow" src="../../static/images/askquestions-icon1.png"></image>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">视频上传:</span>
				<view class="sqr_video">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;" src="../../static/images/askquestions-icon2.png"></image>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">文档上传:</span>
				<view class="sqr_video">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;" src="../../static/images/askquestions-icon3.png"></image>
				</view>
			</view>
			
			<view class="selLis">
				<view class="qst">公开意向</view>
				<view class="r-selt">
					<view class="selt">
						<image src="../../static/images/appeal-icon4.png" mode=""></image>公开
					</view>
					<view class="selt">
						<image src="../../static/images/appeal-icon5.png" mode=""></image>不公开
					</view>
				</view>
			</view>
			<view class="selLis">
				<view class="qst">是否保密</view>
				<view class="r-selt">
					<view class="selt">
						<image src="../../static/images/appeal-icon4.png" mode=""></image>是
					</view>
					<view class="selt">
						<image src="../../static/images/appeal-icon5.png" mode=""></image>否
					</view>
				</view>
			</view>
			<view class="tipsTex">您所提交的事项，信息及办理过程将在网站及手机端公开，可能涉及相关隐私，如涉及他人隐私，须征得本人同意。请慎重选择公开功能。如果您的个人信息需要保密，可以在"是否保密”选项中选择是，我们将对您个人资料采取保密措施。</view>
			<view class="tabbar flex flexCenter" style="" >
				<view class="askquestion flex flexCenter">提交</view>
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
				array: ['请选择','类型一', '类型二', '类型三', '类型四'],
				index: 0
			};
		},
		methods: {
			bindPickerChange: function(e) {
				console.log('picker发送选择改变，携带值为', e.target.value)
				this.index = e.target.value
			}
		}
	}
</script>

<style scoped>
	@import "../../assets/style/public.css";
	.container{padding:0 30rpx;background: #ffffff;}
	.sqr_common{font-size: 28rpx;color: #222222;}
	.list_item{justify-content: space-between;padding: 40rpx 0;border-bottom: solid 1px #EAEAEA;align-items: flex-start;font-size: 28rpx;}
	.list_item input{width: 100%;font-size: 28rpx; color: #333; text-align: right;}
	.list_item .arrow{width: 20rpx;height: 13rpx;margin-left: 20rpx;}
	.sqr_name{color: #999999;text-align: right;}
	.sqr_time{font-size: 28rpx;color: #222222;}
	.list_item textarea{width:536rpx;height:250rpx;font-size: 28rpx;color: #333;background: #F5F5F5;text-align: left;padding:20rpx 10rpx;text-indent: 10rpx;box-sizing: border-box;}
	.tabbar{width: 100%;background-color: white;}
	.askquestion{width: 600rpx;height: 80rpx;background: #ca1c1d;border-radius: 10rpx; margin: 40rpx auto 100rpx auto;font-size: 30rpx;color: #FFFFFF;}
	
	.tipsTex{ color: #999; line-height: 44rpx;padding: 30rpx 0;border-top: 2rpx solid #eaeaea; margin-top: 30rpx;}
	
	.selLis{line-height: 84rpx;text-align: center;display: flex; justify-content: space-between; align-items: center;  height: 80rpx;padding-top: 30rpx;}
	
	.selLis .qst{ line-height: 40rpx; font-size: 28rpx; padding-bottom: 10rpx;}
	.radio{margin:0 30rpx; font-size: 26rpx;}
	

	
</style>