<template>
	<view>
		<text class="button" :class="{active:item.active}" v-for="(item,index) in TabButton" :key="index" @click="getTabButton(item)">
			{{item.text}}
		</text>
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				Bo: '实用工具',
				Lo: '小工具在手，问题不再有',
				show: false
			};
		},
		props: {
			TabButton: Array,
			index: Number
		},
		methods: {
			getTabButton(e) {
				this.$emit("getTabButton", e);
			},

		}
	}
</script>

<style lang="less">
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
</style>
