<template>
	<view class="CourseEntrance-box-Title clearfix">
		<view class="fontTitle">
			<text class="Bo"> {{Bo}} </text> <text class="Lo"> {{Lo}} </text>
		</view>

		<view class="fontButton" v-show="show" >
			<text class="text">更多 </text>
			<text class="iconfont fontButtonicon icon-chevron-right
			"></text>
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
			Bo: String,
			Lo: String,
			show: Boolean
		},
		mounted() {

		}
	}
</script>

<style lang="scss">
	$topColor:#01aefb;
	$bgcColor:#fff;
	$fontColor:#999;
	$fontBColor:#333;

	.CourseEntrance-box-Title {
		.fontTitle {
			float: left;
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
		.fontButton{
			float: right;
			padding-top: 15rpx;
			.text{
				font-size: 25rpx;
				color: $fontColor;
			}
			.fontButtonicon{
				font-size: 25rpx;
				color: $fontColor;
			}
		}

	}
</style>
