<template>
	<view class="BottomNavigation">

		<view class="uni-flex uni-row Navigation">
			<view class="Navigationconer" style="-webkit-flex: 1;flex: 1;" v-for="(item,index) in NavigationData " :key='index'>
				<text class="iconfont fontsize" :class="item.icon"></text>
				<view class="text">
					{{item.text}}
				</view>
			</view>
		</view>
		
	</view>

</template>

<script>
	export default {
		data() {
			return {
				NavigationData: [{
						id: 1,
						icon: 'icon-release',
						url: '',
						text: '首页'
					},
					{
						id: 2,
						icon: 'icon-calendar1',
						url: '',
						text: '课程'
					},
					{
						id: 3,
						icon: 'icon-plus-aquare',
						url: '',
						text: '动态'
					},
					{
						id: 4,
						icon: 'icon-comment',
						url: '',
						text: '问答'
					},
					{
						id: 5,
						icon: 'icon-cloud',
						url: '',
						text: '我的'
					},
				]
			};
		}
	}
</script>

<style lang="less">
	.BottomNavigation {
			margin-top: 150rpx;
			
			width: 100%;
			position: fixed;
			bottom: 0;
			background-color: #FFFFFF;

			.Navigation {
				.Navigationconer{
					text-align: center;
					padding:  15rpx 0;
					.fontsize{
						font-size: 45rpx;
						color: #ABB7BC;
						line-height:1rpx;
					}
					.text{
						color: #ABB7BC;
						
					}
				}
			}
		}

</style>
