
<script>
	import token from "./common/token.js"
	export default {
		onLaunch: function() {	
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import "/assets/style/style.css";
	.ql-editor img{max-width: 100%; display: block;margin: 0 auto;}
	.ql-editor p{max-width: 100%; display: block;margin: 0 auto;}
	.banner .swiper-box .uni-swiper-dots-horizontal{right: 0;left: auto;bottom: 28rpx;}
	uni-tabbar .uni-tabbar__icon{width: 46rpx;height: 46rpx;}
</style>
