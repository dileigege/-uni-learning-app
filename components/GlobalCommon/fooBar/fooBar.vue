<template>
	<view class="bottom">
		<view class="nav-box">
			<view class="nav-tab" v-for="(item,index) in boter" :key='index' :class="{'nav-tab-active': index == invitationtop}" @click="toIndex(index,item)">
				<view class="nav-icon">
					<view class="circle">
						<i :class="'iconfont icon-' + item.icon" />
					</view>
				</view>
				<view class="nav-text">
					{{item.name}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		components: {},
		props:{
			invitationtop: Number,
		},
		data() {
			return {
				activeindex : 0,
				boter: [
					{
						id: 0,
						icon: 'bookmark',
						name: '首页',
						url: '/pages/index/index'
					},
					{
						id: 1,
						icon: 'shu',
						name: '分类',
						url: '/pages/index/index'
					},
					{
						id: 2,
						icon: 'chaxun',
						name: '搜索',
						url: '/pages/index/index'
					},
					{
						id: 3,
						icon: 'briefcase',
						name: '问答',
						url: '/pages/index/index'
					},
					{
						id: 4,
						icon: 'copyright-mark',
						name: '我的',
						url: '/pages/user/user'
					},
				]
			}
		},
		onLoad() {},
		methods: {
			toPage(url) {
				uni.navigateTo({
					url
				})
			},
			toIndex(index, item) {
				console.log(item)
				if (index == 2) {
					uni.switchTab({
						url: '/pages/search/index'
					});
				} else if (index == 0) {
					uni.switchTab({
						url: '/pages/index/index'
					});
				} else if (index == 1) {
					uni.switchTab({
						url: '/pages/course/course'
					});
					console.log(index)

				} else if (index == 3) {
					uni.switchTab({
						url: '/pages/Question/index'
					});

				} else {
					uni.switchTab({
						url: '/pages/user/user'
					});
				}
				this.$emit('toIndex', index)

			}
		}
	}
</script>

<style scoped lang="scss">
	.bottom {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		width: 100%;
		height: 140rpx;
		box-shadow: 0px -2px 6px rgba(125, 125, 125, 0.35);
		background: #fff;
		z-index: 10;
	}

	.nav-tab {
		fiex: 1;
		text-align: center;
		width: 100%;
		height: 50rpx;
	}

	.nav-icon {
		height: 30px;
		color: #333;
		box-sizing: border-box;
		padding: 4px 0 2px 0;
	}

	.nav-icon .iconfont {
		font-size: 20px;
	}

	.nav-text {
		font-size: 11px;
		height: 19px;
		color: #000;
		font-weight: 400;
	}

	.nav-tab-active .circle {
		height: 38px;
		width: 38px;
		line-height: 38px;
		position: relative;
		top: -14px;
		left: calc(50% - 19px);
		border-radius: 50%;
		background: #4da0ff;
		box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2);
	}

	.nav-tab-active .iconfont {
		color: #fff;
	}

	.nav-tab-active .nav-text {
		color: #4da0ff;
	}

	.nav-box {
		/* position: absolute; */
		display: flex;
		width: 100%;
		box-sizing: border-box;
	}

	/*苹果x适配 H5APP*/
	@media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
		.bottom {
			height: 150rpx + 150rpx;
		}
	}

	/*苹果xs适配 H5APP*/
	@media only screen and (device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 3) {
		.bottom {
			height: 150rpx + 150rpx;
		}
	}

	/*苹果xr适配 H5APP*/
	@media only screen and (device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 2) {
		.bottom {
			height: 150rpx + 150rpx;
		}
	}
</style>
