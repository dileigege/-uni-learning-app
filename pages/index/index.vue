<template>
	<view id="Home">

		<!-- 课程入口 开始 -->
		<view class="CourseEntrance">
			<!--  分类 组件  -->
			<tabLink :CourseEntranceData='CourseEntranceData' :id='id' :type='type' :title='title'> 
			</tabLink> 
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
				id:0,
				type:'search',
				title:'同步教辅',
				CourseEntranceData: [
					{
						id: 1,
						type: 'search',
						title: '同步教辅'
					}, {
						id: 2,
						type: 'search',
						title: '同步数学'
					},
					{
						id: 3,
						type: 'search',
						title: '同步英语'
					},
				]
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


			
		}
	}
</style>
