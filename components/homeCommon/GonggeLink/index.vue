<template>
	<view class="GonggeLink">

		<titleList :Bo="Bo" :Lo="Lo">
		</titleList>
		<view class="example-body">
			<uni-grid :column="4" :show-border="false" :square="false" @change="change">
				<uni-grid-item v-if="index < 8" v-for="(item ,index) in list" :index="index" :key="index">
					<view class="grid-item-box">
						<image class="image" :src="item.url" mode="aspectFill" />
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
				Bo: '实用工具',
				Lo: '小工具在手，问题不再有',
			};
		},
		props: {
			list: Array,
			index: Number
		},
		methods: {
			change(e) {
				 let {index} = e.detail
				 this.list[index].badge && this.list[index].badge++
				 this.$emit("changeindex",index);
			},
		
		}
	}
</script>

<style lang="less">
	.GonggeLink {
		margin-top: 25rpx;
		width: 100%;
		background-color: #FFFFFF;

		.grid-item-box {
			flex: 1;
			/* #ifndef APP-NVUE */
			display: flex;
			/* #endif */
			flex-direction: column;
			align-items: center;
			justify-content: center;
			padding: 15px 0;
		}

		.text {
			font-size: 26rpx;
			margin-top: 10rpx;
		}

		.image {
			width: 50rpx;
			height: 50rpx;
		}
	}
</style>
