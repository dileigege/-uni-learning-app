<template>
	<view id="QuestionHome">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="title">
					<text class="titlePiv"> 社区 </text>
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
		<view class="hotQuestion-hotTopic">
			<view class="hotQT-title  uni-flex uni-row full-justified">
				<text class="text">热门话题</text>
				<text class="iconfont fontButtonicon icon-chevron-right">更多</text>
			</view>

		</view>


		<!-- 热门话题  -->

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
		.hotQuestion-hotTopic{
			padding:  15rpx 30rpx;
			border-bottom: 1rpx #e8e8e8 solid;
			.fontButtonicon{
				font-size: 30rpx;
			}
			.text{
				font-size: 30rpx;
			}
		}
	}
</style>
