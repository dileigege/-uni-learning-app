<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/* 官方css  */
	@import url("./common/css/uni.css");
	/* 动画css  */
	@import url("./common/css/animate.css");
	/* 图标css */
	@import url("./common/css/icon.css");
	/* 自定义css  */
	@import url("./common/css/style.scss");
	
	.uni-tabbar{
		display: none;
	}
</style>
