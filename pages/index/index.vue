<template>
	<view id="Home">


		<!-- 课程入口 开始 -->
		<view class="CourseEntrance clearfix">
			<!--  分类 组件  -->
			<tabLink :CourseEntranceData='CourseEntranceData' :id='id' :type='type' :title='title'>
			</tabLink>
		</view>

		<!-- 课程活动轮播  开始 -->
		<view class="ActivityCarousel">
			<view class="uni-margin-wrap">
				<swiper class="swiper" circular :indicator-dots="true" :autoplay="false" :interval="2000">
					<swiper-item>
						<view class="swiper-item">
							
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>

	</view>

</template>

<script>
	import tabLink from '@/components/homeCommon/tablink/index.vue'
	export default {
		components: {
			tabLink
		},
		data() {
			return {
				id: 0,
				type: 'icon-shuxue',
				title: '同步教辅',
				CourseEntranceData: [{
						id: 1,
						type: 'icon-shuxue',
						title: '同步教辅'
					}, {
						id: 2,
						type: 'icon-pawn',
						title: '同步数学'
					},
					{
						id: 3,
						type: 'icon-yingyu',
						title: '同步英语'
					},
				],
			};
		},
		methods: {
			
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
		background-color: #f9f9f9;

		.CourseEntrance {
			// background-color: $topColor;
			background-image: url(../../static/Snipaste_2.jpg);
			height: 150rpx;
		}

		.ActivityCarousel {
			margin-top: 300rpx;
			
			.uni-margin-wrap {
				width: 690rpx;
				margin: 0 30rpx;
			}
			.swiper {
				height: 300rpx;
			}

			.swiper-item {
				position: absolute;
				display: block;
				height: 300rpx;
				line-height: 300rpx;
				text-align: center;
			}

			.swiper-list {
				margin-top: 40rpx;
				margin-bottom: 0;
			}

			.uni-common-mt {
				margin-top: 60rpx;
				position: relative;
			}

			.info {
				position: absolute;
				right: 20rpx;
			}

			.uni-padding-wrap {
				width: 550rpx;
				padding: 0 100rpx;
			}
		}

	}
</style>
