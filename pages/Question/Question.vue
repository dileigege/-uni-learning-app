<template>
	<view id="Question">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="return">
					<text class="iconfont returnicon icon-shu"></text>
				</view>
				<view class="title">
					<text class="titlePiv"> 问答详情 </text>
				</view>
				<view class="button">
					<text class="iconfont buttonicon icon-menu-hamburger"></text>
				</view>
			</view>
		</view>

		<!-- 提问  -->
		<view class="bgc">
		</view>
		
		<view class="quiz">

			<view class="ask">
				问
			</view>
			<view class="quizH1">有没有可以摘抄下来的神仙句子?</view>
			<view class="quizfin">
				很惊艳的那种，想让你快乐 但是不想让别人给你带来快乐，最近经常莫名的笑，原来是又想起你了。 ​​​
			</view>
			<view class="label">
				<text class='text'> 语文 </text>
				<text class='text'> 句子迷 </text>
				<text class='text'> 句子 </text>
				<text class='text'> 文学 </text>
			</view>

			<view class="buttoniober clearfix">
				<view class="text">
					<text class="font mr-2">16K人关注</text> <text class="font mr-2"> 2条评论</text> <text class="font mr-2">3M次浏览</text>
				</view>
				<view class="button">
					我来回答
				</view>
			</view>

		</view>

		<!-- 回答 -->
		<view class="answer">
			<!-- answerTop -->
			<answerTop :fler='fler'>
			</answerTop>
			<!-- boler 文章列表  -->
			<boler :bolerData='bolerData'>
			</boler>
			
			<!-- <view class="loadMore">
				加载更多
			</view> -->
		</view>

		<!-- 更多提问列表 -->
		<view class="">

		</view>

		<!-- 底部导航 -->
		<BottomNavigation>
		</BottomNavigation>
	</view>
</template>

<script>
	import answerTop from '../../components/Questioncomponents/answerTop/index.vue'
	import boler from '../../components/Questioncomponents/boler/index.vue'
	// 底部导航
	import BottomNavigation from '@/components/GlobalCommon/BottomNavigation/index.vue'
	export default {
		components: {
			answerTop,
			boler,
			BottomNavigation,
		},
		data() {
			return {
				fler: {
					digital: 125
				},
				bolerData: [{
						id: 1,
						title: '人之所以伤心，是因为看得不够远。',
						img: [{
								url: '../../static/home/wallhaven-1k3ovv.jpg',
							},
							{
								url: '../../static/home/wallhaven-1k3ovv.jpg',
							}, {
								url: '../../static/home/wallhaven-1k3ovv.jpg',
							},

						],
						nevin: '(无关风月) 1.少年就是少年，他们看春风不喜，看夏蝉不烦，看秋风不悲，看冬雪不叹，看满身富贵懒察觉，看不公不允敢面对，只因他...',
						HeadPortrait: '../../static/home/Avatar1.jpg',
						name: '坠入银河',
						userButton: [{
								Icon: 'link2',
							},
							{
								Icon: 'schedule',
							}, {
								Icon: 'flash_on',
							}
						]
					},

					{
						id: 2,
						title: '少年就是少年，他们看春风不',
						img: [],
						nevin: '(无关风月) 1.少年就是少年，他们看春风不喜，看夏蝉不烦，看秋风不悲，看冬雪不叹，看满身富贵懒察觉，看不公不允敢面对，只因他...',
						HeadPortrait: '../../static/home/Avatar2.jpg',
						name: '严选推荐',
						userButton: [{
								Icon: 'link2',
							},
							{
								Icon: 'schedule',
							}, {
								Icon: 'flash_on',
							}
						]
					},

					{
						id: 3,
						title: '少年就是少年，他们看春风不',
						img: [],
						nevin: '《漫步的艺术》收录了梭罗漫步一生所写的文章，关于山川、溪水、冬雪、森林..在他笔下，↑自然、人交融汇合，浑然- -体，写出了最深刻...',
						HeadPortrait: '../../static/home/Avatar0.jpg',
						name: '一直懒懒',
						userButton: [{
								Icon: 'link2',
							},
							{
								Icon: 'schedule',
							}, {
								Icon: 'flash_on',
							}
						]
					},
				]
			};
		},
		methods: {},
		mounted() {
			console.log(this.bolerData)
		}
	}
</script>

<style lang="less">
	#Question {
		// background-color: #999;
		background-color: #f9f9f9;
		padding-bottom: 100rpx;
		// background-color: #007AFF;

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
				width: 50rpx;
				line-height: 85rpx;
				margin-right: 25rpx;
				color: #333;

				.buttonicon {
					font-size: 30rpx;
				}
			}
		}
		.bgc{
			background-image: url(../../static/home/wallhaven-dpgw2j.jpg);
			background-size: 100% 100%;
			-webkit-filter: blur(10rpx);
			filter: blur(8rpx);
			height: 450rpx;
			position: relative;
			top: 0;
		}

		.quiz {
			margin-top: 4rpx;
			// background-color: #FFFFFF;
			padding: 25rpx;
			position: absolute;
			top: 100rpx;

			// transform: scale(1.2);



			.ask {
				position: absolute;
				top: 40rpx;
				right: 0rpx;
				background-color: #4CD964;
				padding: 5rpx 15rpx;
				font-size: 25rpx;
				color: #FFFFFF;
				border-radius: 45rpx 0 0 45rpx;
			}

			.quizH1 {
				font-size: 40rpx;
				font-weight: 800;
				color: #333333;
			}

			.quizfin {
				color: #666666;
				padding-bottom: 25rpx;
			}

			.label {
				.text {
					font-size: 25rpx;
					background-color: #999999;
					color: #f9f9f9;
					padding: 10rpx 15rpx;
					border-radius: 45rpx;

					margin-right: 15rpx;
				}
			}

			.buttoniober {
				margin: 25rpx 0;
				border-radius: 5rpx;
				border: 1rpx #999 dashed;
				padding: 15rpx;

				.text {
					float: left;

					.font {
						font-size: 24rpx;
						line-height: 25rpx;
					}
				}

				.button {
					float: right;
					font-size: 24rpx;
					line-height: 55rpx;
					color: #f0e2d5;
				}
			}
		}

		.answer {
			background-color: #FFFFFF;
			padding: 15rpx 25rpx;
			margin-top: 10rpx;
			.loadMore{
				height: 75rpx;
				line-height: 75rpx;
				text-align: center;
				color:#666666;
				padding-top: 10rpx;
				border-top: 1rpx solid #ebebeb;
			}

		}
	}
</style>
