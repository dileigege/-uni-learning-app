<template>
	<view id="calculator">
		<!-- 顶部导航条  -->
		<view class="searchTop">
			<view class="uni-flex uni-row">
				<view class="return">
					<text class="iconfont returnicon icon-chevron-left
"></text>
				</view>
				<view class="title">
					<text class="titlePiv"> 计算器 </text>
				</view>
				<view class="button">
					<text class="iconfont buttonicon icon-menu-hamburger"></text>
				</view>
			</view>
		</view>
		<view class="calculator-border">
			<!-- 显示器 -->
			<view class="calculator-display">
				<view class="calculator-formula" v-cloak>{{ formula }}</view>
				<view class="calculator-result" v-cloak>{{ result }}</view>
			</view>
			<!-- 按键 -->
			<view class="calculator-items">
				<view class="calculator-row-1 uni-flex uni-row">
					<view class="flex button whiteButton" @click="drop()">←</view>
					<view class=" flex button whiteButton" @click="cleanResult()">CE</view>
					<view class=" flex button whiteButton" @click="cleanAll()">C</view>
					<view class=" flex button whiteButton" @click="toggle()">±</view>
					<view class=" flex button blueButton " @click="square()">√</view>
				</view>

				<view class="calculator-row-2 uni-flex uni-row">
					<view class=" flex button whiteButton" @click="operate(7)">7</view>
					<view class=" flex button whiteButton" @click="operate(8)">8</view>
					<view class=" flex button whiteButton" @click="operate(9)">9</view>
					<view class=" flex button whiteButton" @click="operate('/')">/</view>
					<view class=" flex button blueButton" @click="operate('%')">%</view>
				</view>

				<view class="calculator-row-3 uni-flex uni-row">
					<view class="flex button whiteButton" @click="operate(4)">4</view>
					<view class="flex button whiteButton" @click="operate(5)">5</view>
					<view class="flex button whiteButton" @click="operate(6)">6</view>
					<view class="flex button whiteButton" @click="operate('*')">*</view>
					<view class="flex button blueButton" @click="devided()">1/x</view>
				</view>

				<view class="calculator-row-4 uni-flex uni-row">
					<view class="flex button whiteButton" @click="operate(1)">1</view>
					<view class="flex button whiteButton" @click="operate(2)">2</view>
					<view class="flex button whiteButton" @click="operate(3)">3</view>
					<view class="flex button whiteButton" @click="operate('-')">-</view>
					<view class="flex button blueButton" @click="operate('+')">+</view>
				</view>

				<view class="calculator-row-5 uni-flex uni-row">
					<view class="nifer whiteButton" @click="operate(0)">0</view>
					<view class="nifer whiteButton" @click="operate('.')">.</view>
					<view class="flex cloernifer blueButton" @click="equal()">=</view>
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
	#calculator{
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
		
					.img {
						margin-top: 25rpx;
						width: 100rpx;
						height: 60rpx;
					}
				}
			}
		
			.button {
				// width: 200rpx;
				line-height: 85rpx;
				margin-right: 35rpx;
				color: #666666;
				margin-top: 15rpx;
		
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
		
		.calculator-border {
			background-color: #f2f2f4;
			width: 100%;
			height: 100%;
			padding-top: 2rpx;
		
			.calculator-display {
				height: 350rpx;
				background-color: #fff;
				text-align: right;
				padding: 25rpx 35rpx;
				padding-top: 0;
				padding-bottom: 95rpx;
		
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
				padding-top: 50rpx;
				
		
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
		
				.calculator-row-1,
				.calculator-row-2,
				.calculator-row-3,
				.calculator-row-4,
				.calculator-row-5 {
					.whiteButton {
						font-size: 40rpx;
						background-color: #FFFFFF;
						color: #64c6f0;
						box-shadow: 0rpx 6rpx 9rpx #e4e4e4;
						
					}
		
					.blueButton {
						font-size: 40rpx;
						background-color: #5ec9f7;
						color: #FFFFFF;
						box-shadow: 0rpx 6rpx 9rpx #b1d6e6;
					}
				}
			}
		}
		
	}

</style>
