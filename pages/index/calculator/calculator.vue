<template>
	<view>
		<view class="calculator-border">
			<view class="calculator-display">
				<view class="calculator-formula" v-cloak>{{ formula }}</view>
				<view class="calculator-result" v-cloak>{{ result }}</view>
			</view>

			<view class="calculator-items">
				<view class="calculator-row-1 uni-flex uni-row">
					<view class="flex button" @click="drop()">←</view>
					<view class=" flex button" @click="cleanResult()">CE</view>
					<view class=" flex button" @click="cleanAll()">C</view>
					<view class=" flex button" @click="toggle()">±</view>
					<view class=" flex button" @click="square()">√</view>
				</view>

				<view class="calculator-row-2 uni-flex uni-row">
					<view class=" flex button" @click="operate(7)">7</view>
					<view class=" flex button" @click="operate(8)">8</view>
					<view class=" flex button" @click="operate(9)">9</view>
					<view class=" flex button" @click="operate('/')">/</view>
					<view class=" flex button" @click="operate('%')">%</view>
				</view>

				<view class="calculator-row-3 uni-flex uni-row">
					<view class="flex button" @click="operate(4)">4</view>
					<view class="flex button" @click="operate(5)">5</view>
					<view class="flex button" @click="operate(6)">6</view>
					<view class="flex button" @click="operate('*')">*</view>
					<view class="flex button" @click="devided()">1/x</view>
				</view>

				<view class="calculator-row-4 uni-flex uni-row">
					<view class="flex button" @click="operate(1)">1</view>
					<view class="flex button" @click="operate(2)">2</view>
					<view class="flex button" @click="operate(3)">3</view>
					<view class="flex button" @click="operate('-')">-</view>
					<view class="flex button" @click="operate('+')">+</view>
				</view>

				<view class="calculator-row-5 uni-flex uni-row">
					<view class="nifer" @click="operate(0)">0</view>
					<view class="nifer" @click="operate('.')">.</view>
					<view class="flex cloernifer" @click="equal()">=</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				formula: "",
				result: 0
			};
		},
		methods: {
			operate(element) {
				console.log("operate..");
				this.formula += element;
				// console.log("this.formula:");
				// console.log(this.formula);
			},

			equal() {
				console.log("equal..");
				this.result = eval(this.formula);
				// console.log("this.formula:");
				// console.log(this.formula);
			},

			cleanResult() {
				console.log("cleanResult..");
				this.result = 0;
			},

			cleanAll() {
				console.log("cleanAll..");
				this.formula = "";
				this.result = 0;
			},

			drop() {
				console.log("drop..");
				this.formula = this.formula.slice(0, -1);
			},

			square() {
				console.log("square..");
				console.log(eval(this.formula));
				eval(this.formula) < 0 ? this.formula = "Can not suqre the negative value" : this.result = Math.sqrt(eval(this.formula));
			},

			devided() {
				console.log("devided..");
				this.formula === "" || this.formula.endsWith("+" || "-" || "*" || "/" || "%") ? {} : this.formula = "1/(" + this.formula +
					")";
				this.equal();
			},

			toggle() {
				console.log("toggle..");


				this.formula === "" || this.formula.endsWith("+" || "-" || "*" || "/" || "%") ? {} : this.formula.startsWith("-") ?
					this.formula = Math.abs(eval(this.formula)).toString() : this.formula = "-(" + this.formula + ")";
				this.equal();
			}

		}
	}
</script>

<style lang="less">
	.calculator-border {
		background-color: #f2f2f4;
		width: 100%;
		height: 100%;

		.calculator-display {
			height: 350rpx;
			// background-color: #EEEEEE;
			text-align: right;
			margin: 25rpx 35rpx;
			margin-top: 0;
			margin-bottom: 95rpx;

			.calculator-formula {
				padding-top: 95rpx;
				font-size: 45rpx;
				color: #68bbec;
			}

			.calculator-result {
				font-size: 75rpx;
				color: #5eaad6;
			}
		}

		.calculator-items {
			// background-color: #FFFFFF;
			margin: 20rpx 35rpx;
			padding-bottom: 150rpx;

			.button {
				height: 80rpx;
				padding: 15rpx;
				background-color: #007AFF;
				line-height: 80rpx;
				margin: 15rpx;
				margin-top: 20rpx;
				margin-bottom: 20rpx;
				border-radius: 50%;
				text-align: center;
				justify-content: center;
				flex-direction: column;
				font-size: 32rpx;

			}

			.nifer {
				text-align: center;
				width: 80rpx;
				height: 80rpx;
				line-height: 80rpx;
				font-size: 32rpx;
				padding: 15rpx;
				background-color: #007AFF;
				margin: 15rpx;
				border-radius: 50%;

			}

			.cloernifer {
				text-align: center;
				width: 80rpx;
				height: 80rpx;
				line-height: 80rpx;
				padding: 15rpx;
				background-color: #007AFF;
				margin: 15rpx;
				border-radius: 40px;
				justify-content: center;
				flex-direction: column;
				font-size: 32rpx;
			}

			.calculator-row-1 {}
		}
	}
</style>
