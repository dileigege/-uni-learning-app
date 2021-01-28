<template>
	<view class="CourseEntrance-box-Title">
		<text class="Bo"> {{Bo}} </text> <text class="Lo"> {{Lo}} </text>
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
</style>
