<template>
	<view class="CourseEntrance-box clearfix">
		<view class="CourseEntrance-box-Title">
			<text class="Bo"> 同步教辅 </text> <text class="Lo"> 全科全面的学习工具 </text>
		</view>
		<view class="CourseEntrance-box-list clearfix">
			<view class="discipline " v-for="(item,index) in CourseEntranceData">
				<view :class="'line'+item.id">
					<!-- <uniIcons class="input-uni-icon" :type="item.type" size="45" color="#fff" /> -->
					<text class="iconfont fontstyle" :class="item.type"> </text>
					<view class="taba"> {{item.title}} </view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniIcons from '@/components/nav_top/uni-icons/uni-icons.vue'

	export default {
		components: {
			uniIcons,
		},
		props: {
			CourseEntranceData: Array,
			type: String,
			title: String,
			id: Number
		},
		mounted(){
			console.log(this.CourseEntranceData)
		}
	}
</script>

<style lang="scss">
	$topColor:#01aefb;
	$bgcColor:#fff;
	$fontColor:#999;
	$fontBColor:#333;

	.CourseEntrance-box {
		position: absolute;
		background-color: $bgcColor;
		width: 85%;
		top: 10px;
		left: 50%;
		transform: translate(-50%);
		padding: 25rpx 35rpx;
		border-radius: 15rpx;
		box-shadow: 1px 2px 9px #e2e2e2;

		.CourseEntrance-box-Title {
			.Bo {
				font-weight: 800;
				font-size: 38rpx;
				color: $fontBColor;
				padding-right: 25rpx;
			}

			.Lo {
				font-weight: 600;
				font-size: 25rpx;
				color: $fontColor;
			}
		}

		.CourseEntrance-box-list {

			.discipline {
				float: left;
				// background-color: #E5E5E5;
				margin: 30rpx 15rpx;
				
				.line1 {
					background-color: #bfa0fe;
					text-align: center;
					padding: 45rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;
					.fontstyle{
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #6c5b91;
					}

				}

				.line2 {
					background-color: #4da0ff;
					text-align: center;
					padding: 45rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;
					.fontstyle{
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #2b5a8f;
					}
				}

				.line3 {
					background-color: #fdbb2f;
					text-align: center;
					padding: 45rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;
					.fontstyle{
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #a77a1e;
					}
				}



				.taba {
					color: #FFFFFF;
					font-weight: 900;
					font-size: 30rpx;
					padding-top: 15rpx;
				}


			}


		}
		// .Moreubjects{
		// 	position: absolute;
		// 	right: 0;
		// 	background-color: $topColor;
		// 	padding: 10rpx 35rpx;
		// 	border-radius: 45rpx;
		// 	color: $bgcColor;
		// 	box-shadow: 1px 2px 9px #e2e2e2;
		// }
	}
</style>
