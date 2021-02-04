<template>
	
</template>

<script>
	import uniIcons from '@/components/nav_top/uni-icons/uni-icons.vue'

	export default {
		components: {
			uniIcons,
		},
		props: {
			// fontTitle:Array,
		},
		data() {
			return {
				fontTitle: [
				  {
					  fontTitle:{
						  Bo: '语文课程',
						  Lo: '爱探索未知的孩子最酷啦',
						  show: false,
					  }
				  }
				]
			}
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
				font-size: 35rpx;
				color: #676767;
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
