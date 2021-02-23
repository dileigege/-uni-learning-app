<template>
	<view id="search">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="return" @click="change">
					<text class="iconfont returnicon icon-left"></text>
				</view>
				<view class="input">
					<input class="uni-input" placeholder="四年级学霸养成营课程" placeholder-style="color:#fff" />
				</view>
				<view class="button">
					搜索
				</view>
			</view>
		</view>

		<!--  搜索历史  -->
		<view class="history">
			<view class="historyTitle uni-flex uni-row ">
				<text class="historyconter"> 搜索历史 </text>
				<text class="iconfont historyIcon icon-close"></text>
			</view>

			<view class="historyLisButton">
				<text class="historyLisButtonli"> 人类科幻2000年 </text>
				<text class="historyLisButtonli"> 精讲“太空漫游”四部曲 </text>
				<text class="historyLisButtonli"> 国学经典 </text>
			</view>
		</view>
		
		<view class="history">
			<view class="historyTitle uni-flex uni-row ">
				<text class="historyconter"> 实时热搜 </text>
			</view>
		
			<view class="historyLisButton">
				<text class="historyLisButtonli"> <text class="iconfont icon-link" style="padding-right: 20rpx;font-size: 25rpx; color: #007AFF;"></text>四年级数学提升课 </text>
				<text class="historyLisButtonli"> 精讲“太空漫游”四部曲 </text>
				<text class="historyLisButtonli"> 名著解读 </text>
				<text class="historyLisButtonli"> 恐龙拯救地球 </text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			change(){
			uni.switchTab({
				url: '/pages/index/index'
			});
			}
		},
		onShow(){
		    uni.hideTabBar()
		},
	}
</script>

<style lang="less">
	#search {
		.searchTop {
			width: 100%;
			background-color: #01AEFB;
			// box-shadow: 1rpx 3rpx 9rpx 1rpx  #00a2e7;
			box-shadow: 1rpx 3rpx 9rpx  #00abef;

			.return {
				width: 50rpx;
				line-height: 85rpx;
				margin-left: 25rpx;
				color: #FFFFFF;
				font-size: 30rpx;
			}

			.input {
				-webkit-flex: 1;
				flex: 1;

				.uni-input {
					border-radius: 45rpx;
					padding: 5rpx;
					padding-left: 35rpx;
					background-color: #69CFFD;
					margin: 15rpx 10rpx;
					color: #FFFFFF;
					font-size: 28rpx;
					line-height: 85rpx;
				}
			}

			.button {
				width: 100rpx;
				color: #FFFFFF;
				font-size: 30rpx;
				margin-left: 25rpx;
				line-height: 90rpx;
			}
		}

		.history {
			padding: 0 35rpx;

			.historyTitle {
				-webkit-justify-content: space-between;
				justify-content: space-between;
				.historyconter{
					font-size: 35rpx;
					font-weight: 800;
					padding-top: 15rpx;
					color: #333333;
				}
				.historyIcon{
					font-size: 35rpx;
					padding-top: 15rpx;
				}
			}
			.historyLisButton{
				.historyLisButtonli{
					display: inline-block;
					padding: 5rpx 25rpx; 
					border-radius: 50rpx;
					margin: 10rpx;
					font-size: 25rpx;
					color: #666666;
					background-color: #EFF4F7;
				}
			}
		}

	}
</style>
