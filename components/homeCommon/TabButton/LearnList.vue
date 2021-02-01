<template>
	<view class="LearnListConter">
		<view class="LearnList uni-flex uni-row" v-for="(item,i) in sortL" :key="i+'data'">
		
			<view class="text uni-flex Imge">
				<image class="Imge" :src="item.url"></image>
			</view>
		
			<view class="uni-flex uni-column LearnList-right">
				<view class="title">
					<view class="titleBl">
						{{item.titleBl}}
					</view>
					<text class="titleDescription"> {{item.smtitle}} </text>
				</view>
				<view class="price">
					<text class="fontsize1">￥</text> <text class="fontsize2"> {{item.price}}</text> <text class="fontsize3">
						￥{{item.originaLprice}} </text>
				</view>
				<view class="wobble">
					{{item.learningNumer}}人已学
				</view>
			</view>
		</view>
	</view>

</template>

<script>
	
	export default {
		data() {
			return {};
		},
		props: {
			sortL: Array,
		},
		methods: {
			getTabButton(e) {
				this.$emit("getTabButton", e);
			},

		}
	}
</script>

<style lang="less">
	.LearnList {
		// background-color:#007AFF;
		padding-top: 45rpx;
		padding-bottom: 25rpx;
		border-bottom: 1rpx solid #f1f1f1;
	
		.uni-flex {
			.Imge {
				margin-left: 10rpx;
				width: 200rpx;
				height: 250rpx;
				border-radius: 5rpx;
			}
		}
	
		.LearnList-right {
			margin-left: 20rpx;
	
			.title {
				.titleBl {
					font-size: 37rpx;
					font-weight: 600;
					line-height: 50rpx;
				}
	
				.titleDescription {
					font-size: 18rpx;
					color: #999999;
	
				}
			}
	
			.price {
				padding: 5rpx 0;
	
				.fontsize1 {
					font-size: 26rpx;
					font-weight: 600;
					color: #FF5942;
				}
	
				.fontsize2 {
					font-size: 50rpx;
					font-weight: 600;
					color: #FF5942;
					vertical-align: text-top;
					padding: 15rpx;
				}
	
				.fontsize3 {
					font-size: 22rpx;
					font-weight: 600;
					color: #C7C7C7;
					vertical-align: bottom;
				}
			}
	
			.wobble {
				font-size: 20rpx;
				color: #999999;
			}
		}
	
	}
	
</style>
