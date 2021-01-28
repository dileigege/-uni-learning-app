<template>
	<view id="Home">


		<!-- 课程入口 开始 -->
		<view class="CourseEntrance clearfix">
			<tabLink :CourseEntranceData='CourseEntranceData' :id='id' :type='type' :title='title'>
			</tabLink>
		</view>
		<!-- 课程活动轮播  开始 -->
		<view class="ActivityCarousel">
			<activity :activity='activity'>
			</activity>
		</view>
	</view>

</template>

<script>
	import tabLink from '@/components/homeCommon/tablink/index.vue';
	import activity from '@/components/homeCommon/activity/index.vue';
	export default {
		components: {
			tabLink,
			activity
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
				activity: [{
						title: "四年级学霸养成营课程15节",
						fontsize2: 1.1,
						fontsize3: 199,
						Avatar: [{
								id: 0,
								url: "../../static/home/Avatar0.jpg",
							},
							{
								id: 1,
								url: "../../static/home/Avatar1.jpg",
							},
							{
								id: 2,
								url: "../../static/home/Avatar2.jpg",
							},
						],
						textFontsize: 30,
						testHour: 1,
						testMinute: 0,
						testSecond: 2,
						testHourday: 5,
					},
					{
						title: "四年级数学课后习题精讲",
						fontsize2: 9.9,
						fontsize3: 199,
						Avatar: [{
								id: 0,
								url: "../../static/home/Avatar0.jpg",
							},
							{
								id: 1,
								url: "../../static/home/Avatar1.jpg",
							},
							{
								id: 2,
								url: "../../static/home/Avatar2.jpg",
							},
						],
						textFontsize: 15,
						testHour: 1,
						testMinute: 0,
						testSecond: 2,
						testHourday: 5,
					},
					{
						title: "40天学会40首古诗",
						fontsize2: 1.1,
						fontsize3: 199,
						Avatar: [{
								id: 0,
								url: "../../static/home/Avatar0.jpg",
							},
							{
								id: 1,
								url: "../../static/home/Avatar1.jpg",
							},
							{
								id: 2,
								url: "../../static/home/Avatar2.jpg",
							},
						],
						textFontsize: 30,
						testHour: 1,
						testMinute: 0,
						testSecond: 2,
						testHourday: 5,
					}

				]
			};
		},
		created() {
			setTimeout(() => {
				this.activity.testHourday
				this.activity.testHour
				this.activity.testMinute
				this.activity.testSecond
			}, 2000)
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
			background-image: url(../../static/Snipaste_2.jpg);
			height: 150rpx;
		}
		.ActivityCarousel {
			margin-top: 300rpx;
			
		}

	}
</style>
