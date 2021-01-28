<template>
	<view class="uni-margin-wrap">
		<swiper class="swiper" circular :indicator-dots="true" :autoplay="false" :interval="2000">
			<swiper-item v-for="(item,index) in activity">
				<view class="swiper-item">
					<view class="activity-title">
						<text class="title"> {{item.title}} </text>
						<view class="text">
							<text class="fontsize1">￥</text> <text class="fontsize2"> {{item.fontsize2}} </text> <text class="fontsize3">
								￥{{item.fontsize3}} </text>
						</view>
						<view class="button">
							我要学
						</view>
					</view>
					<view class="activity-content">
						<view class="Avatar">
							<text v-for="(imgages,index) in item.Avatar">
								<image class="img" :src="imgages.url" mode=""></image>
							</text>
							<text class="text"> 已服务超21.2万同学 </text>
						</view>
						<text class="text"> 名额仅剩</text> <text class="textFontsize"> {{item.textFontsize}} </text> <text class="text"> 位
						</text>
						<view class="Countdown clearfix">
							<view class="example-liter">
								<text class="iconfont icon-calendar1"></text> 倒计时：
							</view>
							<view class="example-body">
								<uni-countdown :minute="item.testMinute" :second="item.testSecond" :hour="item.testHour" :show-colon="false"
								 :day="item.testHourday" />
							</view>

						</view>
					</view>
				</view>
			</swiper-item>
		</swiper>
	</view>

</template>

<script>
	import uniCountdown from '@/components/nav_top/uni-countdown/uni-countdown.vue'
	export default {
		components: {
			uniCountdown
		},
		props: {
			activity: Array
		},

		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.uni-margin-wrap {
		width: 700rpx;
		margin: 0 30rpx;

		.swiper {
			height: 460rpx;

			.swiper-item {
				position: absolute;
				display: block;
				background-color: #FFFFFF;

				.activity-title {
					background-color: #f96029;
					color: #FFFFFF;
					padding: 10rpx 35rpx;
					width: 630rpx;
					border-radius: 15rpx 15rpx 0 0;

					.title {
						font-size: 38rpx;
						font-weight: 800;
					}

					.text {
						padding-top: 15rpx;

						.fontsize1 {
							font-size: 22rpx;
							font-weight: 600;

						}

						.fontsize2 {
							font-size: 60rpx;
							font-weight: 600;
							color: #fff512;
							vertical-align: text-top;
							padding: 15rpx;
						}

						.fontsize3 {
							font-size: 22rpx;
							font-weight: 600;
							color: #fff512;
						}
					}

					.button {
						background-color: #fff512;
						display: inline-block;
						padding: 15rpx 45rpx;
						border-radius: 45rpx;
						color: #6d3e1c;
						font-size: 20rpx;
						position: absolute;
						top: 55rpx;
						right: 15rpx;

					}

				}

				.activity-content {
					background-color: #FFFFFF;

					.Avatar {
						padding: 15rpx 35rpx;
						padding-right: 25rpx;
						display: inline-block;

						.img {
							width: 55rpx;
							height: 55rpx;
							border-radius: 50%;
							border: 1px #f96029 solid;
							margin-left: -15rpx;
							vertical-align: middle;
						}

						.text {
							padding-left: 15rpx;
							font-size: 20rpx;
							line-height: 55rpx;
							vertical-align: middle;
							color: #666666;
							padding-right: 15rpx;
							border-right: 1rpx #c7c7c7 solid;
						}
					}

					.text {
						font-size: 30rpx;
						font-weight: 600;
						color: #333333;

					}

					.textFontsize {
						font-size: 35rpx;
						font-weight: 700;
						color: #6D3E1C;
						background-color: #E5E5E5;
						padding: 10rpx;
						margin: 10rpx;
					}

					.Countdown {
						display: inline-block;
						border-radius: 45rpx;
						color: #999999;
						margin-top: 10rpx;
						margin-bottom: 20rpx;
						// margin-left: 50%;
						width: 100%;

						// transform: translate(-50%);
						.example-liter {
							font-size: 30rpx;
							line-height: 60rpx;
							margin-left: 20rpx;
							float: left;
						}

						.example-body {
							float: left;
						}

					}
				}
			}

			.swiper-list {
				margin-top: 40rpx;
				margin-bottom: 0;
			}
		}
	}
</style>
