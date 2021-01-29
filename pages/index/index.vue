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

			<!-- 列表 -->
			<view class="learningLi">
				<view class="TabButton">
					<!-- tab 按钮  -->
					<text class="button" :class="{active:item.active}" v-for="(item,index) in TabButton" :key="index" @click="getTabButton(item)">
						{{item.text}}
					</text>

					<view class="LearnList uni-flex uni-row" v-for="(item,i) in sortL" :key="i+'data'">

						<view class="text uni-flex Imge">
							<image class="Imge" :src="item.url"></image>
						</view>

						<view class="uni-flex uni-column LearnList-right">
							<view class="title">
								<view class="titleBl">
									{{item.titleBl}}
								</view>

								<text class="titleDescription"> {{item.smtitle}} </text>
							</view>

							<view class="price">
								<text class="fontsize1">￥</text> <text class="fontsize2"> {{item.price}}</text> <text class="fontsize3">
									￥{{item.originaLprice}} </text>
							</view>

							<view class="wobble">
								{{item.learningNumer}}人已学
							</view>

						</view>
					</view>


				</view>


			</view>
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
				
				sortL: [
					{
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

					.button {
						padding: 10rpx 20rpx;
						border-radius: 45rpx;
						border: 1rpx solid #B3BFC3;
						margin-left: 15rpx;
						color: #B3BFC3;
						font-size: 25rpx;
					}

					.active {
						padding: 10rpx 20rpx;
						border-radius: 45rpx;
						background-color: #03AEFB;
						border: 1rpx solid #03AEFB;
						margin-left: 15rpx;
						color: #FFFFFF;
					}

					.LearnList {
						// background-color:#007AFF;
						padding-top: 45rpx;
						padding-bottom: 25rpx;
						border-bottom: 1rpx solid #f1f1f1;

						.uni-flex {
							.Imge {
								margin-left: 10rpx;
								width: 200rpx;
								height: 250rpx;
								border-radius: 5rpx;
							}
						}

						.LearnList-right {
							margin-left: 20rpx;

							.title {
								.titleBl {
									font-size: 37rpx;
									font-weight: 600;
									line-height: 50rpx;
								}

								.titleDescription {
									font-size: 18rpx;
									color: #999999;

								}
							}

							.price {
								padding: 5rpx 0;

								.fontsize1 {
									font-size: 26rpx;
									font-weight: 600;
									color: #FF5942;
								}

								.fontsize2 {
									font-size: 50rpx;
									font-weight: 600;
									color: #FF5942;
									vertical-align: text-top;
									padding: 15rpx;
								}

								.fontsize3 {
									font-size: 22rpx;
									font-weight: 600;
									color: #C7C7C7;
									vertical-align: bottom;
								}
							}

							.wobble {
								font-size: 20rpx;
								color: #999999;
							}
						}

					}

				}
			}
		}


	}
</style>
