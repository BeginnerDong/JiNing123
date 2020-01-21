<template>
	<view>
		<view class="container">
			<view class="list_item flex">
				<view class="sqr_common">诉求人:</view>
				<view class="rr sqr_name">
					<input type="text" placeholder="请输入诉求人姓名" v-model="submitData.name">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">来电时间:</span>
				<view class="rr sqr_time">
					<input type="date" :value="currentDate" disabled="true">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">时间:</span>
				<view class="rr sqr_time flex" @click="openDatetimePicker">
					<input :value="submitData.record_time" disabled="true">

					<image class="arrow" src="../../static/images/appeal-icon1.1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">事发地址:</span>
				<view class="rr sqr_name flex" @click="chooseAddress">
					{{submitData.address!=''?submitData.address:'请选择'}}
					<image class="arrow" src="../../static/images/appeal-icon1.1.png"></image>
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">问题标题:</span>
				<view class="rr sqr_name">
					<input type="text" placeholder="请输入问题标题" v-model="submitData.title">
				</view>
			</view>
			<view class="list_item flex">
				<view class="contact_area">
					<span class="sqr_common">反映内容:</span>
				</view>
				<view class="sqr_name">
					<textarea value="" placeholder="请输入问题内容" v-model="submitData.content" />
					</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">诉求目的:</span>
				<view class="sqr_name">
					<input type="text" placeholder="请输入诉求目的" v-model="submitData.purpose">
				</view>
			</view>
			<view class="list_item flex">
				<span class="sqr_common">类型:</span>
				<view class="sqr_name flex">
					<view class="uni-list">
						<view class="uni-list-cell">
							<view class="uni-list-cell-db">
								<picker @change="bindPickerChange" :value="index" :range="array">
									<view class="uni-input">{{array[indexLabel]?array[indexLabel]:'请选择'}}</view>
								</picker>
							</view>
						</view>
					</view>
					<!-- 请选择 -->
					<image class="arrow" src="../../static/images/appeal-icon1.1.png"></image>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">视频上传:</span>
				<view class="sqr_video">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;"  @click="upLoadImg('video')" src="../../static/images/appeal-icon3.1.png" 
					v-if="submitData.mainImg.length==0"></image>
					<video style="width: 156rpx;height:156rpx;" :src="submitData.mainImg[0].url" v-if="submitData.mainImg.length>0"></video>
				</view>
			</view>
			<view class="list_item">
				<span class="sqr_common">文档上传:</span>
				<view class="sqr_video" @click="upLoadImg('other')">
					<view style="width: 100%;height: 30rpx;"></view>
					<image style="width: 156rpx;height:156rpx;" v-if="submitData.banner_Img.length==0" 
					src="../../static/images/appeal-icon3.png"></image>
					<image style="width: 156rpx;height:156rpx;" v-if="submitData.banner_Img.length>0"
					:src="submitData.banner_Img[0].url"></image>
				</view>
			</view>
			
			<view class="selLis">
				<view class="qst">公开意向</view>
				<view class="r-selt">
					<view class="selt" @click="change('1')">
						<image :src="submitData.public==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>公开
					</view>
					<view class="selt" @click="change('2')">
						<image :src="submitData.public==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>不公开
					</view>
					
				</view>
			</view>
			<view class="selLis">
				<view class="qst">是否保密</view>
				<view class="r-selt">
					<view class="selt" @click="secrecy('1')">
						<image :src="submitData.secret==1?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'"  mode=""></image>是
					</view>
					<view class="selt"  @click="secrecy('2')">
						<image :src="submitData.secret==2?'../../static/images/appeal-icon4.png':'../../static/images/appeal-icon5.png'" mode=""></image>否
					</view>
				</view>
			</view>
			<view class="tipsTex">您所提交的事项，信息及办理过程将在网站及手机端公开，可能涉及相关隐私，如涉及他人隐私，须征得本人同意。请慎重选择公开功能。如果您的个人信息需要保密，可以在"是否保密”选项中选择是，我们将对您个人资料采取保密措施。</view>
			<view class="tabbar flex flexCenter" style="" >
				<view class="askquestion flex flexCenter" @click="Utils.stopMultiClick(submit)">提交</view>
			</view>
		</view>
		<button>
		</button>
		<simple-datetime-picker
		   ref="myPicker"
		   @submit="handleSubmit"
		   :start-year="2000"
		   :end-year="2030"
		   color="red"
		></simple-datetime-picker>
	</view>
</template>

<script>
	import simpleDatetimePicker from "@/components/buuug7-simple-datetime-picker/simple-datetime-picker.vue"
	export default {
		components: {
			simpleDatetimePicker
		},
		data() {
			return {
				Router:this.$Router,
				Utils:this.$Utils,
				currentDate: '',
				array: ['咨询','投诉', '建议', '求助', '表扬','其他'],
				submitData:{
					name:'',
					record_time:'',
					address:'',
					title:'',
					content:'',
					purpose:'',
					behavior:'',
					mainImg:[],
					banner_Img:[],
					public:'2',
					secret:'2',
					city_id:'0',
					country_id:'0',
					town_id:'0',
					type:1
				},
				indexLabel:''
			};
		},
		
		
		onLoad(){
			const self = this;
			var date=new Date();		
			var year=date.getFullYear();
			var month=date.getMonth()+1;
			var day=date.getDate();	
			var hour=date.getHours();
			var minute=date.getMinutes();
			var second=date.getSeconds();
			if (hour<10) {
				hour='0'+hour;
			}
			if (minute<10) {
				minute='0'+minute;
			}
			if (second<10) {
				second='0'+second;
			}
			
			self.currentDate=year+'-'+month+'-'+day+' '+hour+':'+minute+':'+second;
			var res = self.$Token.getProjectToken(function() {
				self.$Utils.loadAll(['getUserData'], self)
			});
			if (res) {
				self.$Utils.loadAll(['getUserData'], self)
			};
		},
		
		methods: {
			
			getUserData() {
				const self = this;
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				const callback = (res) => {
					if (res.solely_code==100000) {
						self.userData = res.info.data[0]
						if(self.userData.area_id==0){
							self.$Utils.finishFunc('getUserData');
							uni.showModal({
							    title: '提示',
							    content: '检测到您还未注册，立即注册吗？',
								confirmColor:'#ca1c1d',
							    success: function (res) {
							        if (res.confirm) {
							            self.Router.reLaunch({route:{path:'/pages/inforRegister/inforRegister'}})
							        } else if (res.cancel) {
							            uni.navigateBack({
							            	delta:1
							            })
							        }
							    }
							});
							return
						}else{
							self.submitData.city_id = self.userData.city_id;
							self.submitData.country_id = self.userData.country_id;
							self.submitData.town_id = self.userData.town_id
						}
					}else{
						self.$Utils.showToast(res.msg, 'none')
					}
					self.$Utils.finishFunc('getUserData');
				};
				self.$apis.userGet(postData, callback);
			},
			
			upLoadImg(type) {
				const self = this;
				
				wx.showLoading({
					mask: true,
					title: '上传中',
				});
				const callback = (res) => {
					console.log('res', res)
					if (res.solely_code == 100000) {
						if(type=='video'){
							self.submitData.mainImg.push(res.info.url)
						}else if(type=='other'){
							self.submitData.banner_Img.push(res.info.url)
						}
						wx.hideLoading()
					} else {
						self.$Utils.showToast('网络故障', 'none')
					}
				};
				if(type=='video'){
					wx.chooseVideo({
						count: 1,
						success: function(res) {
							console.log(res);
							var tempFilePaths = res.tempFilePath;
							console.log(callback)
							self.$Utils.uploadFile(tempFilePaths, 'file', {
								tokenFuncName: 'getProjectToken',
								type:type
							}, callback)
						},
						fail: function(err) {
							wx.hideLoading();
						},
						
					})
				}else{
					wx.chooseImage({
						count: 1,
						success: function(res) {
							console.log(res);
							var tempFilePaths = res.tempFilePaths;
							console.log(callback)
							self.$Utils.uploadFile(tempFilePaths[0], 'file', {
								tokenFuncName: 'getProjectToken',
								type:type
							}, callback)
						},
						fail: function(err) {
							wx.hideLoading();
						},
						
					})
				}
				
			},
			
			submit() {
				const self = this;
				uni.setStorageSync('canClick', false);
				var newObject = self.$Utils.cloneForm(self.submitData);
				delete newObject.mainImg;
				delete newObject.banner_Img;
				const pass = self.$Utils.checkComplete(newObject);
				console.log('pass', pass);
				console.log('self.submitData',self.submitData)
				if (pass) {						
					
					self.messageAdd();
					
				} else {
					uni.setStorageSync('canClick', true);
					self.$Utils.showToast('请补全信息', 'none')
				};
			},
					
			messageAdd() {
				const self = this;
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				/* if(!wx.getStorageSync('user_info')||!wx.getStorageSync('user_info').headImgUrl){
				  postData.refreshToken = true;
				}; */
				postData.data = {};
				postData.data = self.$Utils.cloneForm(self.submitData);
				const callback = (data) => {				
					if (data.solely_code == 100000) {	
						uni.setStorageSync('canClick', true);
						uni.showModal({
						    title: '提示',
						    content: '当前时间'+self.$Utils.formatTime()+'济宁市政务服务热线办公室已查收信件',
							confirmColor:'#ca1c1d',
							showCancel:false,
						    success: function (res) {
						        if (res.confirm) {
						            self.Router.reLaunch({route:{path:'/pages/index/index'}})
						        } else if (res.cancel) {
						           
						        }
						    }
						});			
					} else {
						uni.setStorageSync('canClick', true);
						self.$Utils.showToast(data.msg, 'none', 1000)
					}	
				};
				self.$apis.messageAdd(postData, callback);
			},
			
			change(curr){
				const self=this
				if(curr!=self.curr){
					self.curr=curr
					self.submitData.public = self.curr
				}
			},
			
			secrecy(index){
				const self=this
				if(index!=self.index){
					self.index=index;
					self.submitData.secret = self.index
				}
			},
			
			openDatetimePicker() {
				this.$refs.myPicker.show();
			},
	
		  // 关闭picker
		  closeDatetimePicker() {
			 this.$refs.myPicker.hide();
		  },
	
		  handleSubmit(e) {
			  const self = this;
			 console.log(e); // {year: "2019", month: "07", day: "17", hour: "15", minute: "21"}
			 self.submitData.record_time = e.year+'-'+e.month+'-'+e.day+' '+e.hour+':'+e.minute;
			 console.log(self.submitData)
		  },
			
			chooseAddress(e) {
				const self = this;
				uni.authorize({
				    scope: 'scope.userLocation',
				    success() {
				        uni.chooseLocation({
				        	success: (res) => {
				        		console.log(111)
				        		self.submitData.address = res.address
				        	},
				        	fail: (e) => {
				        		uni.getSetting({
				        			success: (res) => {
				        				console.log(res)
				        				let locaAuth = res.authSetting['scope.userLocation']
				        				if (locaAuth) {/* 判断位置是否已经授权，是选择地图位置点击取消触发的fail，再选择位置 */
				        					console.log('地图点击取消')
				        					uni.chooseLocation({
				        						success: (res) => {
				        							self.submitData.address = res.address
				        						},
				        					});
				        				}
				        				if (!locaAuth) { /* 如果地理位置没授权 */
				        					console.log(222)
				        					uni.showModal({
				        					    title: '提示',
				        					    content: '需要授权位置信息',
				        						confirmColor:'#ca1c1d',
				        						showCancel:true,
				        					    success: function (res) {
				        					        if (res.confirm) {
				        					            uni.openSetting({
				        					            	success: (res) => {
				        					            		console.log(res.authSetting)
				        					            	},
				        					            	fail: (res) => {
				        					            		console.log(res)
				        					            	},
				        					            });
				        					        } else if (res.cancel) {
				        					           
				        					        }
				        					    }
				        					});			
				        					
				        				
				        				}
				        			}
				        		})
				        	}
				        });
				    },
					fail: (e) => {
						uni.showModal({
						    title: '提示',
						    content: '需要授权位置信息',
							confirmColor:'#ca1c1d',
							showCancel:true,
						    success: function (res) {
						        if (res.confirm) {
						            uni.openSetting({
						            	success: (res) => {
						            		console.log(res.authSetting)
						            	},
						            	fail: (res) => {
						            		console.log(res)
						            	},
						            });
						        } else if (res.cancel) {
						           
						        }
						    }
						});
					}
				})
				
			},
			
			
			chooseLocation(){
				
				const self = this;
				uni.chooseLocation({
				    success: function (res) {
				        console.log('位置名称：' + res.name);
				        console.log('详细地址：' + res.address);
				        console.log('纬度：' + res.latitude);
				        console.log('经度：' + res.longitude);
						self.submitData.address = res.address
				    },
					fail() {
						uni.authorize({
						    scope: 'scope.userLocation',
						    success() {
						      uni.chooseLocation({
						          success: function (res) {
						              console.log('位置名称：' + res.name);
						              console.log('详细地址：' + res.address);
						              console.log('纬度：' + res.latitude);
						              console.log('经度：' + res.longitude);
						      		self.submitData.address = res.address
						          },
								})
						    }
						})
					}
				});
			},
			
			
			bindPickerChange: function(e) {
				const self = this;
				console.log('picker发送选择改变，携带值为', e.target.value)
				self.indexLabel = e.target.value;
				self.submitData.behavior = parseInt(e.target.value)+1
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
