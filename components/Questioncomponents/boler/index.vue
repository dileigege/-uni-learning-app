<template>
	<view >
		<view class="boler" v-for="(item,index) in bolerData" :key='index'>
			<view class="answer">
				答
			</view>
			<view class="content">
				<view class="title">
					{{item.title}}
				</view>
				<view class="imgArrange uni-flex uni-row">
					<image class="flex lerImage" v-for="(item1 , index1) in item.img" :key='index1' :src="item1.url" mode=""></image>
				</view>
				<view class="nevin">
					<text>{{item.nevin}}</text>
				</view>
			</view>
			<view class="user uni-flex uni-row full-justified">
				<view class="HeadPortrait">
					<image class="img" :src="item.HeadPortrait" mode=""></image>
					<text class="name"> {{item.name}} </text>
				</view>
		
				<view class="userButton">
					<text v-for="(item2, index2) in item.userButton " :key="index2" class="iconfont Icon" :class=" 'icon-'+ item2.Icon "></text>
				</view>
		
			</view>
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
			bolerData:Array,
		}
		
		
	}
</script>

<style lang="less">
.boler{
	position: relative;
	.answer{
		position: absolute;
		top: 20rpx;
		right: -24rpx;
		background-color: #007AFF;
		color: #FFFFFF;
		padding: 8rpx 15rpx;
		border-radius: 50rpx 0  0 50rpx;
		line-height: 30rpx;
	}
	
	.user {
		padding-bottom: 10rpx;
		.HeadPortrait {
			.img {
				width: 50rpx;
				height: 50rpx;
				border-radius: 50rpx;
				margin: 15rpx;
				vertical-align: middle;
			}
	
			.name {
				vertical-align: middle;
				font-size: 20rpx;
			}
		}
	
		.userButton {
			font-size: 28rpx;
			margin-right: 10rpx;
			margin-top: 15rpx;
	
			.Icon {
				font-size: 30rpx;
				margin-right: 10rpx;
			}
		}
	}
	
	.content {
		border-top: 2rpx solid #f1f1f1;
	
		.title {
			font-size: 30rpx;
			font-weight: 600;
			padding-top: 15rpx;
		}
	
		.lerImage {
			margin: 10rpx;
			height: 150rpx;
			border-radius: 5rpx;
		}
	
		.nevin {
			font-size: 24rpx;
			color: #101010;
		}
	}
	
}
</style>
