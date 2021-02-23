<template>
	<view id="User"> 
		<!-- 底部导航 -->
		<foo-bar @toIndex="toIndex"  :invitationtop='invitationtop'></foo-bar>
	</view>
</template>

<script>
	// 底部导航
	import fooBar from '@/components/GlobalCommon/fooBar/fooBar.vue'
	export default {
		components: {
			fooBar
		},
		data() {
			return {
				invitationtop:4,
			};
		},
		methods:{
			toIndex(index){
				this.index = index
				console.log(index)
			},
		}
	}
</script>

<style lang="less">
#User {

}
</style>
