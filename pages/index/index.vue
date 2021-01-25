<template>
	<view id="Home">

		<!-- 课程入口 开始 -->
		<view class="CourseEntrance">
			<view class="CourseEntrance-box">
				<view class="CourseEntrance-box-Title">
					<text class="Bo"> 同步教辅 </text> <text class="Lo"> 全科全面的学习工具 </text>
				</view>
				<view class="CourseEntrance-box-list clearfix">
					<view class="discipline line1">
						<uni-icons class="input-uni-icon" type="search" size="45" color="#666666" />
						<view> 同步教辅 </view>
					</view>

					<view class="discipline line2">
						<uni-icons class="input-uni-icon" type="search" size="45" color="#666666" />
						<view> 同步数学 </view>
					</view>

					<view class="discipline line3">
						<uni-icons class="input-uni-icon" type="search" size="45" color="#666666" />
						<view> 同步英语 </view>
					</view>
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
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	$topColor:#01aefb;
	$bgcColor:#fff;
	$fontColor:#999;
	$fontBColor:#333;

	/* 声明清除浮动的样式 */
	.clearfix:before,
	.clearfix:after {
		content: "";
		display: table;
	}

	.clearfix:after {
		clear: both;
	}

	/* ie6 7 专门清除浮动的样式*/
	.clearfix {
		*zoom: 1;
	}


	#Home {
		background-color: #e6e6e6;

		.CourseEntrance {
			background-color: $topColor;
			height: 150rpx;

			.CourseEntrance-box {
				position: absolute;
				background-color: $bgcColor;
				width: 80%;
				top: 10px;
				left: 50%;
				transform: translate(-50%);
				padding: 25rpx 35rpx;
				border-radius: 15rpx;

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
						text-align: center;
						width: 25%;
						// background-color: #E5E5E5;
						margin: 30rpx 10rpx;
						padding: 45rpx 15rpx;
						font-size: 20rpx;
						font-weight: 800;
						border-radius: 10rpx;
						.input-uni-icon{
							font-weight: 900;
						}
						
					}

					.ine1 {
						background-color: ;
					}
				}

			}
		}
	}
</style>
