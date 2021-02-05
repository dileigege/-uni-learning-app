<template>
	<view id="QuestionHome">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="title">
					<text class="titlePiv"> LOGO </text>
				</view>
				<view class="button clearfix ">
					<view class="button1">
						<text class="iconfont buttonicon icon-briefcase"></text>
						<text class="buttonText">问答</text>
					</view>
					<view class="button1">
						<text class="iconfont buttonicon icon-baby-formula"></text>
						<text class="buttonText">话题</text>
					</view>
				</view>
			</view>
		</view>
		<!-- 本周精选 -->
		<view class="select">
			<!-- 轮播图 -->
			<proj-activities :ProjectActivities='ProjectActivities'>
			</proj-activities>
		</view>

		<!-- 热门问答  -->
		<view class="hotQuestion-hotTopic" v-for="(item,index) in hotQuestionHotTopic" :key='index'>

			<view class="hotQT-title  uni-flex uni-row full-justified" v-show="item.hotQTitle.sower == true">
				<text class="text"> {{item.hotQTitle.Title}} </text>
				<text class="iconfont fontButtonicon icon-chevron-right">更多</text>
			</view>

			<view class="hotQT-list-ler">
				<view class="hotQT-list-title">
					{{item.hotQTListLer}}
				</view>
				<view class="uni-flex uni-row hotQT-list-conter">
					<image class="flex-imges img" :src="item.url" mode=""></image>
					<view class="uni-flex uni-column flex-text text">
						<text>{{item.hotQTListText}}​​​</text>
					</view>
				</view>

			</view>

			<view class="hotQT-buttons uni-flex uni-row full-justified pa-tB">
				<view class="IconText">
					<text class="iconfont icon-paperclip Icon"></text>
					<text class="text mr-2"> {{item.reply}} 回复 </text>
					<text class="text mr-2"> {{item.comments}} 评论 </text>
				</view>
				<view class="Icons">
					<text class=" iconfont Icon icon-heart-empty"></text>
					<text class=" iconfont Icon icon-publish"></text>
				</view>

			</view>

		</view>

		<!-- 底部导航 -->
		<BottomNavigation>
		</BottomNavigation>
	</view>
</template>

<script>
	// 专题活动
	import ProjActivities from '@/components/homeCommon/ProjActivities/index.vue';
	// 底部导航
	import BottomNavigation from '@/components/GlobalCommon/BottomNavigation/index.vue'
	export default {
		components: {
			ProjActivities,
			BottomNavigation,
		},
		data() {
			return {
				ProjectActivities: [{
						id: 1,
						url: '../../static/home/wallhaven-1k3ovv.jpg',
						title: '秀出你的作文',
						text: '秀出你的作文，一起参与活动赢，文具相机呀',
						countdown: '08:45:27',
						iscountdownTrue: false,
						isboer: false
					},
					{
						id: 2,
						url: '../../static/home/wallhaven-wqy6d7.jpg',
						title: '快来一起玩吧',
						text: '小学宝线下积木PK大赛正式开始，快来一起玩吧',
						countdown: '08:45:27',
						iscountdownTrue: false,
						isboer: false
					},
					{
						id: 3,
						url: '../../static/home/wallhaven-e7ymvo.jpg',
						title: '暑假已到',
						text: '暑假已到，跟同学们一起逛馆，你还等什么',
						countdown: '08:45:27',
						iscountdownTrue: false,
						isboer: false
					}
				],
				hotQuestionHotTopic: [{
						id: 1,
						hotQTitle: {
							sower: true,
							Title: '热门问答',
						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
					{
						id: 2,
						hotQTitle: {
							sower: false,

						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
					
					{
						id: 3,
						hotQTitle: {
							sower: false,
					
						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
					
					{
						id: 4,
						hotQTitle: {
							sower: true,
							Title: '热门话题',
						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
					
					{
						id: 5,
						hotQTitle: {
							sower: false,
						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
					
					{
						id: 6,
						hotQTitle: {
							sower: false,
						},
						hotQTListLer: '有没有可以摘抄下来的神仙句子?',
						hotQTListText: '很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​',
						reply: 125,
						comments: 900,
						url: '../../static/home/wallhaven-dpgw2j.jpg'
					},
				]
			}
		},
		methods: {

		}
	}
</script>

<style lang="less">
	#QuestionHome {
		.searchTop {
			width: 100%;
			background-color: #FFFFFF;
			// box-shadow: 1rpx 3rpx 9rpx 1rpx  #00a2e7;
			box-shadow: 1rpx 3rpx 9rpx #EEEEEE;


			.return {
				width: 50rpx;
				line-height: 85rpx;
				margin-left: 25rpx;
				color: #333;

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
					color: #333;
				}
			}

			.button {
				width: 200rpx;
				line-height: 85rpx;
				margin-right: 35rpx;
				color: #666666;

				.button1 {
					float: left;
					margin-right: 15rpx;
				}

				.buttonicon {
					font-size: 30rpx;
					line-height: 85rpx;
				}
			}
		}

		.hotQuestion-hotTopic {
			padding: 15rpx 30rpx;

			.hotQT-title {
				padding-bottom: 15rpx;
				border-bottom: 1rpx #e8e8e8 solid;

				.fontButtonicon {
					font-size: 30rpx;
				}

				.text {
					font-size: 30rpx;
				}
			}

			.hotQT-list-ler {
				.hotQT-list-conter {
					.img {
						width: 150rpx;
						height: 150rpx;
						border-radius: 5rpx;
					}

					.text {
						margin-left: 25rpx;
						font-size: 28rpx;
					}

				}

				.hotQT-list-title {
					font-size: 38rpx;
					line-height: 85rpx;
					font-weight: 300;
					color: #666666;
				}
			}

			.hotQT-buttons {
				border-bottom: 1rpx solid #e2e2e2;

				.IconText {
					font-size: 25rpx;
					color: #666666;

					.text {
						font-size: 25rpx;
						color: #d37b62;
					}

				}

				.Icons {
					.Icon {
						font-size: 50rpx;
						line-height: 58rpx;
						color: #666666;
					}
				}
			}

		}
	}
</style>
