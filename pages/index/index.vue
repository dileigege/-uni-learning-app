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
			<!-- 列表 -->
			<view class="learningLi">
				<view class="TabButton">
					<!-- tab 按钮  -->
					<TabButton :TabButton='TabButton' @getTabButton='getTabButton'>
					</TabButton>
					<!--  tab 列表 -->
					<LearnList :sortL='sortL'>
					</LearnList>
				</view>


			</view>
		</view>

		<!-- 专题活动  -->
		<view class="ProjectActivities">

			<proj-activities :ProjectActivities='ProjectActivities'>

			</proj-activities>

		</view>
	</view>

</template>

<script>
	// 同步教辅 
	import tabLink from '@/components/homeCommon/tablink/index.vue';
	// 课程活动轮播
	import activity from '@/components/homeCommon/activity/index.vue';
	// 实用工具
	import GonggeLink from '@/components/homeCommon/GonggeLink/index.vue';
	// 课外学习
	import TabButton from '../../components/homeCommon/TabButton/tabButton.vue';
	import LearnList from '../../components/homeCommon/TabButton/LearnList.vue';
	// 专题活动
	import ProjActivities from '../../components/homeCommon/ProjActivities/index.vue';

	export default {
		components: {
			tabLink,
			activity,
			GonggeLink,
			TabButton,
			LearnList,
			ProjActivities

		},
		data() {
			return {
				id: 0,
				type: 'icon-shuxue',
				title: '同步教辅',
				index: 0,
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
						bacColor: "#D7F3FF"
					},
					{
						url: 'icon-jisuanqi',
						text: '计算器',
						badge: '1',
						type: "success",
						fontColor: "#4D9FFF",
						bacColor: "#E9F6FC"
					},
					{
						url: 'icon-chaxun',
						text: '单词查询',
						badge: '99',
						type: "warning",
						fontColor: "#FEBC30",
						bacColor: "#FFF3D9"
					},
					{
						url: 'icon-align-center',
						text: '语文作文',
						badge: '2',
						type: "error",
						fontColor: "#BEA0FE",
						bacColor: "#F5F0FF",

					},
					{
						url: 'icon-maobi',
						text: '古文助手',
						fontColor: "#BEA0FE",
						bacColor: "#F5F0FF"
					},
					{
						url: 'icon-ad',
						text: '英语作文',
						fontColor: "#FEBC30",
						bacColor: "#FFF3D9"
					},
					{
						url: 'icon-shu',
						text: '汉语字典',
						fontColor: "#BEA0FE",
						bacColor: "#F5F0FF"
					},
					{
						url: 'icon-blackboard',
						text: '心算练习',
						fontColor: "#4D9FFF",
						bacColor: "#E9F6FC"
					},
				],
				TabButton: [{
						id: 1,
						text: "科幻故事",
						active: true,
					},
					{
						id: 2,
						text: "国学经典",
						active: false,
					},
					{
						id: 3,
						text: "名著解读",
						active: false,
					},
					{
						id: 3,
						text: "历史地理",
						active: false,
					},
				],
				sortL: [{
						uid: 1,
						sort: "科幻故事",
						upDate: false, // 最新 
						Hottest: false, // 最热
						titleBl: '一本正经的外星人课',
						smtitle: '科学的星际交流指南',
						price: 19.8,
						originaLprice: 198,
						learningNumer: 67343,
						url: "../../static/home/Avatar0.jpg",


					},
					{
						uid: 2,
						sort: "科幻故事",
						upDate: false, // 最新 
						Hottest: false, // 最热
						titleBl: '精讲“太空漫游”四部曲',
						smtitle: '科学的星际交流指南',
						price: 19.8,
						originaLprice: 198,
						learningNumer: 67343,
						url: "../../static/home/Avatar1.jpg",
					},
					{
						uid: 3,
						sort: "科幻故事",
						upDate: false, // 最新 
						Hottest: false, // 最热
						titleBl: '自然界的奥秘',
						smtitle: '自然界太多未知的东西吸引着我们去探索',
						price: 19.8,
						originaLprice: 198,
						learningNumer: 67343,
						url: "../../static/home/Avatar2.jpg",
					},

					{
						uid: 4,
						sort: "科幻故事",
						upDate: false, // 最新 
						Hottest: false, // 最热
						titleBl: '恐龙拯救地球',
						smtitle: '你知道吗，恐龙竟然要拯救地球？',
						price: 19.8,
						originaLprice: 198,
						learningNumer: 67343,
						url: "../../static/home/Avatar1.jpg",
					},

					{
						uid: 5,
						sort: "科幻故事",
						upDate: false, // 最新 
						Hottest: false, // 最热
						titleBl: '恐龙拯救地球2 ',
						smtitle: '你知道吗，恐龙竟然要拯救地球？',
						price: 19.8,
						originaLprice: 198,
						learningNumer: 67343,
						url: "../../static/home/Avatar1.jpg",
					},
				],
				ProjectActivities: [{
						id: 1,
						url: '../../static/home/wallhaven-1k3ovv.jpg',
						text: '秀出你的作文，一起参与活动赢，文具相机呀',
						countdown: '08:45:27',
					},
					{
						id: 2,
						url: '../../static/home/wallhaven-wqy6d7.jpg',
						text: '小学宝线下积木PK大赛正式开始，快来一起玩吧',
						countdown: '08:45:27',
					},
					{
						id: 3,
						url: '../../static/home/wallhaven-e7ymvo.jpg',
						text: '暑假已到，跟同学们一起逛馆，你还等什么',
						countdown: '08:45:27',
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
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
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
			getTabButton(e) {
				e.active = !e.active
			}
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

		.learning {
			background-color: #FFFFFF;

			.CourseEntrance-box-Title {
				padding: 15rpx 45rpx;
			}

			.learningLi {
				padding-left: 25rpx;
				padding-right: 25rpx;

				.TabButton {
					padding-top: 25rpx;
				}
			}
		}

		.ProjectActivities {
			margin-top: 35rpx;

			background-color: #FFFFFF;

			.CourseEntrance-box-Title {
				padding: 25rpx 40rpx;
			}

			.Projectfer-box {
				.scroll-view_H {
					white-space: nowrap;
					width: 100%;
				}

				.scroll-view-item_H {
					display: inline-block;
					margin: 20rpx;
					margin-left: 40rpx;
					width: 550rpx;
					font-size: 36rpx;
					margin-top: 0;
					padding-bottom: 25rpx;

					box-shadow: 1rpx 2rpx 9rpx 3rpx #e5e5e5;
					border-radius: 15rpx;

					&:last-child {
						margin-right: 40rpx;
					}

					.imges-view {
						uni-image {
							height: 250rpx;
							width: 100%;
							border-radius: 15rpx 15rpx 0 0;
						}
					}

					.text-view {
						font-size: 30rpx;
						word-wrap: break-word;
						word-break: break-all;
						padding: 0 15rpx;
						color: #333333;
						font-weight: 300;
						white-space: normal;
					}

					.countdown {
						padding: 0 15rpx;
						font-size: 25rpx;
						padding-top: 10rpx;
						color: #333333;
						font-weight: 300;
					}

				}
			}
		}

	}
</style>
