<template>
	<view class="CourseEntrance-box clearfix">
		
		<titleList :Bo="Bo" :Lo="Lo" :show="show">
		</titleList>
		
		<view class="CourseEntrance-box-list clearfix">
			<view class="uni-flex uni-row">
				<view class="text uni-flex" v-for="(item,index) in CourseEntranceData" :key="index">
					<view :class="'line'+item.id">
						<text class="iconfont fontstyle" :class="item.type"> </text>
						<view class="taba"> {{item.title}} </view>
					</view>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	import uniIcons from '@/components/nav_top/uni-icons/uni-icons.vue';
	import titleList from '@/components/homeCommon/titletext/index.vue'

	export default {
		components: {
			uniIcons,
			titleList,
		},
		data() {
			return {
				Bo:'同步教辅',
				Lo:'全科全面的学习工具',
				show : false
			}
		},
		props: {
			CourseEntranceData: Array,
			type: String,
			title: String,
			id: Number
		},
		mounted() {
			console.log(this.CourseEntranceData)
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

	.CourseEntrance-box {
		position: absolute;
		background-color: $bgcColor;
		width: 85%;
		top: 10px;
		left: 50%;
		transform: translate(-50%);
		padding: 20rpx 35rpx;
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

			.flex-item {
				width: 33.3%;
				height: 200rpx;
				text-align: center;
				line-height: 200rpx;
			}



			.text {
				margin: 15rpx 10rpx;
				text-align: center;
				color: #FFFFFF;
				-webkit-flex: 1;
				flex: 1;
				-webkit-justify-content: center;
				justify-content: center;
				-webkit-align-items: center;
				align-items: center;
				line-height: 1rem;

				.line1 {
					background-color: #bfa0fe;
					text-align: center;
					padding: 35rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;

					.fontstyle {
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #8d78bf;
					}

				}

				.line2 {
					background-color: #4da0ff;
					text-align: center;
					padding: 35rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;

					.fontstyle {
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #3b7fc7;
					}
				}

				.line3 {
					background-color: #fdbb2f;
					text-align: center;
					padding: 35rpx 32rpx;
					font-size: 20rpx;
					font-weight: 800;
					border-radius: 10rpx;
					box-shadow: 1px 2px 9px #c7c7c7;

					.fontstyle {
						color: #FFFFFF;
						font-size: 90rpx;
						font-weight: 300;
						text-shadow: 1px 2px 9px #d99e26;
					}
				}

			}



			// .discipline {
			// 	float: left;
			// 	// background-color: #E5E5E5;
			// 	margin: 30rpx 15rpx;

			// 	.line1 {
			// 		background-color: #bfa0fe;
			// 		text-align: center;
			// 		padding: 45rpx 32rpx;
			// 		font-size: 20rpx;
			// 		font-weight: 800;
			// 		border-radius: 10rpx;
			// 		box-shadow: 1px 2px 9px #c7c7c7;
			// 		.fontstyle{
			// 			color: #FFFFFF;
			// 			font-size: 90rpx;
			// 			font-weight: 300;
			// 			text-shadow: 1px 2px 9px #8d78bf;
			// 		}

			// 	}

			// 	.line2 {
			// 		background-color: #4da0ff;
			// 		text-align: center;
			// 		padding: 45rpx 32rpx;
			// 		font-size: 20rpx;
			// 		font-weight: 800;
			// 		border-radius: 10rpx;
			// 		box-shadow: 1px 2px 9px #c7c7c7;
			// 		.fontstyle{
			// 			color: #FFFFFF;
			// 			font-size: 90rpx;
			// 			font-weight: 300;
			// 			text-shadow: 1px 2px 9px #3b7fc7;
			// 		}
			// 	}

			// 	.line3 {
			// 		background-color: #fdbb2f;
			// 		text-align: center;
			// 		padding: 45rpx 32rpx;
			// 		font-size: 20rpx;
			// 		font-weight: 800;
			// 		border-radius: 10rpx;
			// 		box-shadow: 1px 2px 9px #c7c7c7;
			// 		.fontstyle{
			// 			color: #FFFFFF;
			// 			font-size: 90rpx;
			// 			font-weight: 300;
			// 			text-shadow: 1px 2px 9px #d99e26;
			// 		}
			// 	}



			// 	.taba {
			// 		color: #FFFFFF;
			// 		font-weight: 900;
			// 		font-size: 30rpx;
			// 		padding-top: 15rpx;
			// 	}


			// }


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
