<template>
	<view id="course">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="return">
					<text class="iconfont returnicon icon-shu"></text>
				</view>
				<view class="title">
					<text class="titlePiv"> 精品课程 </text>
				</view>
				<view class="button">
					<text class="iconfont buttonicon icon-menu-hamburger"></text>
				</view>
			</view>
		</view>
		
		<!--  tab切换  -->
		<view class="courseTab">
			<!-- tab 按钮  -->
			<view class="TabButtonList">
				<TabButton :TabButton='TabButton' @getTabButton='getTabButton'>
				</TabButton>
			</view>
			<!-- 邀请 开始  -->
			<invitation :invitation='invitation'>
			</invitation>
		</view>

		<!--  tab文章页   -->
		<view class="courselist" v-for="(item,index) in courselist" :key='index'>
			<view class="courselistTitle">
				<view class="CourseEntrance-box-Title clearfix">
					<view class="fontTitle">
						<text class="Bo">{{item.fontTitle.Bo}} </text> <text class="Lo">{{item.fontTitle.Lo}}  </text>
					</view>
					<view class="fontButton" v-show="item.fontTitle.show">
						<text class="text">更多 </text>
						<text class="iconfont fontButtonicon icon-chevron-right
						"></text>
					</view>
				</view>
			</view>
			<view class="uni-flex uni-row courseContent">
				<view class="courseContentleft uni-flex">
					<view class="courseIcon" :style="[{ backgroundColor: item.courseIcon.background, boxShadow: item.courseIcon.shadow + '5rpx 1px 3px'}]">
						<view class="text" :style="[{borderBottom: item.courseIcon.shadow + '5rpx solid'}]">
							难度<text>{{item.courseIcon.number}}</text>星
						</view>
						<!-- text-shadow: 5rpx 1rpx 3rpx #a0a0a0c4; -->
						<view class="iconfont Icon" :class="'icon-'+ item.courseIcon.IconName" :style="[{color: item.courseIcon.iconColor,textShadow:item.courseIcon.shadow + '5rpx 1px 3px'}]"></view>
						<view class="line" :style="[{backgroundColor: item.courseIcon.line}]"></view>
					</view>
				</view>
				<view class="uni-flex uni-column courseContreght">
					<view class="courseContreghtTitle">
						{{item.courseContreght.courseContreghtTitle}}
					</view>
					<view class="coursebrief">
						{{item.courseContreght.coursebrief}}
					</view>
					<view class=" difficulty">
						<view class="text">
							<text>难度</text>
							<text>{{item.courseContreght.difficulty}}</text>
						</view>
						<view class="rate">
							<uni-rate v-model="item.courseContreght.value" size="18" :readonly="true" />
						</view>

					</view>
					<view class="button">
						<text class="text">{{item.courseContreght.button1}} </text>
						<text class="text">{{item.courseContreght.button2}} </text>
					</view>
				</view>
			</view>
		</view>
		
		<!-- 专题活动 开始 -->
		<view class="ProjectActivities">
			<proj-activities :ProjectActivities='ProjectActivities'>
			</proj-activities>
		</view>
		
		<!-- 底部导航 -->
	<foo-bar @toIndex="toIndex" :invitationtop='invitationtop'></foo-bar>

	</view>
</template>

<script>
	import TabButton from '@/components/homeCommon/TabButton/tabButton.vue';
	// import titleList from '@/components/courseComponents/titletext/index.vue';
	import invitation from '../../components/courseComponents/invitation/invitation.vue';
	// 底部导航
	import fooBar from '@/components/GlobalCommon/fooBar/fooBar.vue';
	// 专题活动
	import ProjActivities from '@/components/homeCommon/ProjActivities/index.vue';
	// 评分 
	import uniRate from '../../components/nav_top/uni-rate/uni-rate.vue'
	export default {
		components: {
			TabButton,
			invitation,
			fooBar,
			ProjActivities,
			uniRate
		},
		data() {
			return {
				value: 2.5,
				invitationtop:1,
				TabButton: [{
						id: 1,
						text: "语文",
						active: true,
					},
					{
						id: 2,
						text: "数学",
						active: false,
					},
					{
						id: 3,
						text: "英语",
						active: false,
					},
					{
						id: 3,
						text: "历史",
						active: false,
					},
				],
				invitation: {
					backgroundColor: '#FFEDDD',
					color: '#FF632B',
					conter: '邀请小伙伴一起学习赠送免费课'
				},
				courselist: [
					{
					fontTitle: {
						Bo: '提升课',
						Lo: '适合成绩70-90分的同学',
						show: false,
					},
					courseIcon:{
						background:'#BEA0FF',
						shadow:'rgb(164 133 239)',
						border: '#ab90e8',
						iconColor: '#D7C5FF',
						line: '#ab90e8',
						number:3,
						IconName: 'blackboard'
					},
					courseContreght:{
						courseContreghtTitle:'四年级数学提升课',
						coursebrief: '名师主讲+辅导老师，打牢数学基础',
						difficulty: '中等',
						value: 2.5,
						button1: '吃透课本',
						button2: '夯实基础',
						
					},
					
					
				},
				
				{
					fontTitle: {
						Bo: '尖子课',
						Lo: '适合成绩90分以上的同学',
						show: false,
					},
					courseIcon:{
						background:'#FEBB30',
						shadow:'rgb(183 130 18)',
						border: '#da9f29',
						iconColor: '#FEBB30',
						line: '#da9f29',
						number:4,
						IconName: 'adjust'
					},
					courseContreght:{
						courseContreghtTitle:'四年级数学尖子课',
						coursebrief: '名师主讲+辅导老师，打牢数学基础',
						difficulty: '较难',
						value: 3,
						button1: '吃透课本',
						button2: '夯实基础',
						
					},
					
					
				},
				
				{
					fontTitle: {
						Bo: '冲顶课',
						Lo: '适合成绩95分以上的同学',
						show: false,
					},
					courseIcon:{
						background:'#65D1FF',
						shadow:'rgb(61 154 193)',
						border:'#4999b9',
						iconColor: '#65D1FF',
						line: '#4087a3',
						number:4,
						IconName: 'dashboard'
					},
					courseContreght:{
						courseContreghtTitle:'四年级数学冲顶课',
						coursebrief: '名师主讲+辅导老师，打牢数学基础',
						difficulty: '困难',
						value: 4.5,
						button1: '深度探究',
						button2: '思维拓展',
						
					},
					
					
				},
				],
				ProjectActivities: [{
						id: 1,
						url: '../../static/home/wallhaven-1k3ovv.jpg',
						text: '秀出你的作文，一起参与活动赢，文具相机呀',
						countdown: '08:45:27',
						iscountdownTrue: true
					},
					{
						id: 2,
						url: '../../static/home/wallhaven-wqy6d7.jpg',
						text: '小学宝线下积木PK大赛正式开始，快来一起玩吧',
						countdown: '08:45:27',
						iscountdownTrue: false
					},
					{
						id: 3,
						url: '../../static/home/wallhaven-e7ymvo.jpg',
						text: '暑假已到，跟同学们一起逛馆，你还等什么',
						countdown: '08:45:27',
						iscountdownTrue: false
					}
				],
			}
		},
		methods: {
			getTabButton(e) {
				e.active = !e.active
			},
			toIndex(index){
				this.index = index
				console.log(index)
			},
		},
		onShow(){
		    uni.hideTabBar()
		},
	}
</script>

<style lang="scss">
	$topColor:#01aefb;
	$bgcColor:#fff;
	$fontColor:#999;
	$fontBColor:#333;

	#course {
		background-color: #f9f9f9;

		.searchTop {
			width: 100%;
			background-color: #01AEFB;
			// box-shadow: 1rpx 3rpx 9rpx 1rpx  #00a2e7;
			box-shadow: 1rpx 3rpx 9rpx #00abef;

			.return {
				width: 50rpx;
				line-height: 85rpx;
				margin-left: 25rpx;
				color: #FFFFFF;

				.returnicon {
					font-size: 35rpx;
				}
			}

			.title {
				-webkit-flex: 1;
				flex: 1;

				.titlePiv {
					text-align: center;
					line-height: 85rpx;
					margin-left: 25rpx;
					color: #FFFFFF;
				}

			}

			.button {
				width: 50rpx;
				line-height: 85rpx;
				margin-right: 25rpx;
				color: #FFFFFF;

				.buttonicon {
					font-size: 30rpx;
				}
			}
		}

		.courseTabTitle {
			margin: 25rpx;
		}

		.courseTab {
			margin-top: 25rpx;

			.TabButtonList {
				padding-left: 15rpx;
			}
		}

		.courselist {
			background-color: #FFFFFF;
			margin: 25rpx;
			padding: 20rpx 25rpx;
			border-radius: 5rpx;

			.courselistTitle {
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

					.fontButton {
						float: right;
						padding-top: 15rpx;

						.text {
							font-size: 25rpx;
							color: $fontColor;
						}

						.fontButtonicon {
							font-size: 25rpx;
							color: $fontColor;
						}
					}

				}
			}

			.courseContent {
				padding-top: 15rpx;

				.courseContentleft {
					width: 200rpx;
					height: 280rpx;
					-webkit-justify-content: center;
					justify-content: center;
					-webkit-align-items: center;
					align-items: center;
					margin-right: 25rpx;

					.courseIcon {
						position: relative;
						width: 200rpx;
						height: 280rpx;
						border-radius: 5rpx;

						.text {
							position: absolute;
							top: 35rpx;
							right: 45rpx;
							padding-bottom: 15rpx;
							font-size: 25rpx;
							color: #FFFFFF;
						}

						.Icon {
							position: absolute;
							right: 15rpx;
							bottom: 75rpx;
							font-size: 135rpx;
							line-height: 0;
						}

						.line {
							width: 10rpx;
							height: 280rpx;
							background-color: #006bdc;
							position: absolute;
							top: 0;
							left: 20rpx;
							line-height: 0rpx;
						}
					}
				}

				.courseContreght {
					-webkit-flex: 1;
					flex: 1;

					// -webkit-justify-content: space-between;
					// justify-content: space-between;
					// background-color: #00ffb7;
					.courseContreghtTitle {
						color: #676767;
						font-size: 38rpx;
						font-weight: 800;
					}

					.coursebrief {
						font-size: 28rpx;
						color: #999;
						// line-height: 60rpx;
					}

					.difficulty {
						font-size: 28rpx;
						color: #999;
						line-height: 60rpx;

						.text {
							float: left;
						}

						.rate {
							padding-top: 10rpx;
							float: left;

						}
					}

					.button {
						color: #666666;
						margin-top: 15rpx;

						.text {
							border: 1rpx solid #999999;
							padding: 5rpx 15rpx;
							border-radius: 50rpx;
							margin-right: 15rpx;

						}
					}

				}
			}

		}
		.ProjectActivities{
			padding-bottom: 150rpx;
		}
	}
</style>
