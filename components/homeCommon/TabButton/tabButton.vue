<template>
	<view>
		<text class="button" :class="{active:item.active}" v-for="(item,index) in TabButton" :key="index" @click="getTabButton(item)">
			{{item.text}}
		</text>
		
	</view>
</template>

<script>
	export default {
		components: {
			
		},
		data() {
			return {
				
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
	.CourseEntrance-box-Title {
		padding: 25rpx 20rpx;
	}
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
