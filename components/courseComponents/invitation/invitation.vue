<template>
	<view class="invitation uni-flex uni-row"  :style="invitation">
		<text class="iconfont icon-hand-right left"> </text>
		<text class="conter" style="color: #333333;"> {{invitation.conter}} </text>
	    <text class="iconfont icon-close"></text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props:{
			invitation:Object,
		}
		
	}
</script>

<style lang="less">
	.invitation{
				margin: 25rpx;
				padding: 10rpx 25rpx;
				border-radius: 5rpx;
				.left{
					display: inline-block;
					width: 50rpx;
					line-height: 55rpx;
				}
				.conter{
					-webkit-flex: 1;
					flex: 1;
					line-height: 55rpx;
				}
				.right{
					display: inline-block;
					width: 50rpx;
					line-height: 55rpx;
					
				}
			}
</style>
