<template>
	<view id="Question">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="return">
					<text class="iconfont returnicon icon-shu"></text>
				</view>
				<view class="title">
					<text class="titlePiv"> 问答 </text>
				</view>
				<view class="button">
					<text class="iconfont buttonicon icon-menu-hamburger"></text>
				</view>
			</view>

		</view>

		<!-- 提问  -->
		<view class="quiz">
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

		<view class="answer ma-LR p-1">
			
			<view class="answerTop">
				
			</view>
			
		</view>
		<!-- 提问列表 -->
		<view class="">

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="less">
	#Question {
		// background-color: #f9f9f9;
		background-color: #007AFF;

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

		.quiz {
			margin-top: 4rpx;
			background-color: #FFFFFF;
			padding: 25rpx;


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
					color: #007AFF;
				}
			}
		}

		.answer {
			background-color: #FFFFFF;
			margin: 15rpx;
		}
	}
</style>
