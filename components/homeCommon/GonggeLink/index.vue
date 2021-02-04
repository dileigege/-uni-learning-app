<template>
	<view class="GonggeLink">

		<titleList :fontTitle='fontTitle'>
		</titleList>
		<view class="example-body">
			<uni-grid :column="4" :show-border="false" :square="false" @change="change">
				<uni-grid-item v-if="index < 8" v-for="(item ,index) in list" :index="index" :key="index">
					<view class="grid-item-box">
						<!-- <image class="image" :src="item.url" mode="aspectFill" /> -->
						<!--  -->
						<text class="iconfont fontbaler" :class="item.url" :style="{ color: item.fontColor, backgroundColor: item.bacColor}" ></text>
						<text class="text">{{item.text}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
	</view>
</template>

<script>
	import uniGrid from '@/components/nav_top/uni-grid/uni-grid.vue';
	import uniGridItem from '@/components/nav_top/uni-grid-item/uni-grid-item.vue';
	import titleList from '@/components/homeCommon/titletext/index.vue'

	export default {
		components: {
			uniGrid,
			uniGridItem,
			titleList
		},
		data() {
			return {
				fontTitle:{
					Bo: '实用工具',
					Lo: '小工具在手，问题不再有',
					show : false
				}
				
			};
		},
		props: {
			list: Array,
			index: Number
		},
		methods: {
			change(e) {
				this.$emit("changeIndex", e);
			},

		}
	}
</script>

<style lang="less">
	.GonggeLink {
		margin-top: 25rpx;
		width: 100%;
		background-color: #FFFFFF;
		padding-bottom: 25rpx;
		
		.CourseEntrance-box-Title{
			padding: 15rpx 45rpx;
		}
		
		.grid-item-box {
			flex: 1;
			/* #ifndef APP-NVUE */
			display: flex;
			/* #endif */
			flex-direction: column;
			align-items: center;
			justify-content: center;
			padding: 15px 0;
			.fontbaler{
				font-size: 45rpx;
				line-height: 45rpx;
				padding: 25rpx;
				border-radius: 50%;
				text-shadow: 1rpx 0 6rpx #efefef;
			}
			.text {
				font-size: 26rpx;
				margin-top: 10rpx;
				color: #666666;
			}

			.image {
				width: 50rpx;
				height: 50rpx;
			}
		}
	}
</style>
