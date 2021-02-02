<template>
	<view class="ProjActivities">

		<titleList :Bo="Bo" :Lo="Lo" :show="show">
		</titleList>
		
		<view class="Projectfer-box">
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="0">
				<view class="scroll-view-item_H" v-for="(item,index) in ProjectActivities" :key='index'>
					<view class="imges-view">
						<image :src="item.url" mode=""></image>
					</view>
					<view class="text-view">
						<text class="font"> 
						{{item.text}}
						</text>
					</view>
					<view class="countdown">
						距活动结束:<text> {{item.countdown}} </text>
					</view>
				</view>
			</scroll-view>
		</view>
		

	</view>
</template>

<script>
	import titleList from '@/components/homeCommon/titletext/index.vue'

	export default {
		components: {
			titleList
		},
		data() {
			return {
				Bo: '专题活动',
				Lo: '学得好，也要玩得好呦~',
				show: true,
				scrollTop: 0,
				old: {
					scrollTop: 0
				},
			};
		},
		props: {
			ProjectActivities: Array,
		},
		methods: {
		scroll: function(e) {
			console.log(e)
			this.old.scrollTop = e.detail.scrollTop
		},
		}
	}
</script>

<style lang="less">
	.CourseEntrance-box-Title {
		padding: 25rpx 40rpx;
	}
	
	.Projectfer-box {
		.scroll-view_H {
			white-space: nowrap;
			width: 100%;
		}
	
		.scroll-view-item_H {
			display: inline-block;
			margin: 20rpx;
			margin-left: 40rpx;
			width: 550rpx;
			font-size: 36rpx;
			margin-top: 0;
			padding-bottom: 25rpx;
	
			box-shadow: 1rpx 2rpx 9rpx 3rpx #e5e5e5;
			border-radius: 15rpx;
	
			&:last-child {
				margin-right: 40rpx;
			}
	
			.imges-view {
				uni-image {
					height: 250rpx;
					width: 100%;
					border-radius: 15rpx 15rpx 0 0;
				}
			}
	
			.text-view {
				font-size: 30rpx;
				word-wrap: break-word;
				word-break: break-all;
				padding: 0 15rpx;
				color: #333333;
				font-weight: 300;
				white-space: normal;
			}
	
			.countdown {
				padding: 0 15rpx;
				font-size: 25rpx;
				padding-top: 10rpx;
				color: #333333;
				font-weight: 300;
			}
	
		}
	}
</style>
