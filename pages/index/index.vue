<template>
	<view id="Home">
		<!-- 同步教辅 开始 -->
		<view class="CourseEntrance clearfix">
			<tabLink :CourseEntranceData='CourseEntranceData' :id='id' :type='type' :title='title'>
			</tabLink>
		</view>
		<!-- 课程活动轮播  开始 -->
		<view class="ActivityCarousel">
			<activity :activity='activity'>
			</activity>
		</view>
		
		<!-- 实用工具  -->
		<GonggeLink :list='list' @changeIndex='changeIndex'>
		</GonggeLink>
		
		<!-- 课外学习  -->
		<view class="learning">
			<titleList :Bo="Bo" :Lo="Lo" :show="show">
			</titleList>
			
		</view>
		
	</view>

</template>

<script>
	import tabLink from '@/components/homeCommon/tablink/index.vue';
	import activity from '@/components/homeCommon/activity/index.vue';
	import GonggeLink from '@/components/homeCommon/GonggeLink/index.vue';
	import titleList from '@/components/homeCommon/titletext/index.vue'
	export default {
		components: {
			tabLink,
			activity,
			GonggeLink,
			titleList
			
		},
		data() {
			return {
				id: 0,
				type: 'icon-shuxue',
				title: '同步教辅',
				index: 0,
				Bo: '课外学习',
				Lo: '爱探索未知的孩子最酷啦',
				show: true,
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

				],
				list: [{
						url: 'icon-paizhao',
						text: '拍照搜题',
						badge: '0',
						type: "primary",
						fontColor: "#03AEFB",
						bacColor:"#D7F3FF"
					},
					{
						url: 'icon-jisuanqi',
						text: '计算器',
						badge: '1',
						type: "success",
						fontColor: "#4D9FFF",
						bacColor:"#E9F6FC"
					},
					{
						url: 'icon-chaxun',
						text: '单词查询',
						badge: '99',
						type: "warning",
						fontColor: "#FEBC30",
						bacColor:"#FFF3D9"
					},
					{
						url: 'icon-align-center',
						text: '语文作文',
						badge: '2',
						type: "error",
						fontColor: "#BEA0FE",
						bacColor:"#F5F0FF",
						
					},
					{
						url: 'icon-maobi',
						text: '古文助手',
						fontColor: "#BEA0FE",
						bacColor:"#F5F0FF"
					},
					{
						url: 'icon-ad',
						text: '英语作文',
						fontColor: "#FEBC30",
						bacColor:"#FFF3D9"
					},
					{
						url: 'icon-shu',
						text: '汉语字典',
						fontColor: "#BEA0FE",
						bacColor:"#F5F0FF"
					},
					{
						url: 'icon-blackboard',
						text: '心算练习',
						fontColor: "#4D9FFF",
						bacColor:"#E9F6FC"
					},
					{
						url: '/static/c9.png',
						text: 'Grid 9'
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
			changeIndex(e) {
				let {
					index
				} = e.detail
				this.list[index].badge && this.list[index].badge++

				uni.showToast({
					title: `点击第${index+1}个宫格`,
					icon: 'none'
				})
			},
		}
	}
</script>

<style lang="scss">
	$topColor:#01aefb;
	$bgcColor:#fff;
	$fontColor:#999;
	$fontBColor:#333;

	#Home {
		background-color: #f9f9f9;

		.CourseEntrance {
			background-image: url(../../static/Snipaste_2.jpg);
			height: 150rpx;
		}

		.ActivityCarousel {
			margin-top: 320rpx;
		}
		.learning{
			background-color: #FFFFFF;
			.CourseEntrance-box-Title{
				padding: 15rpx 45rpx;
			}
			
		}


	}
</style>
