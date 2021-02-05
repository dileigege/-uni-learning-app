<template>
	<view class="answerTop  uni-flex  full-justified">
		<view class="text1">
			回答 {{fler.digital}}
		</view>
		<view class="text2">
			排序
			<text class="iconfont icon-chevron-down"></text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		props:{
			fler:Object,
		}
	}
</script>

<style lang="less">
	.answerTop {
		background-color: #FFFFFF;
		padding-bottom: 10rpx;

		.text1 {
			color: #101010;
			font-size: 25rpx;
			line-height: 52rpx;
		}

		.text2 {
			color: #999898;
			font-size: 28rpx;
		}
	}
</style>
