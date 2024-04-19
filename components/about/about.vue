<template>
	<view class="page">
		<view class="body">
			<image src="https://shuguo888.top/image/R-C.jpg" mode="aspectFill"></image>
			<view class="box">
				<view class="result">识别结果:</view>
				<view class="end">{{contents}}</view>
			</view>
		</view>
		<view>
			<Alldetail></Alldetail>
		</view>
	</view>
</template>

<script>
	export default {
		name:"about",
		data() {
			return {
				contents:"疾病内容"
			};
		}
	}
</script>

<style lang="scss">
.body{
	display: flex;
	flex-direction: column;
	// height: 500rpx;
	// width: 750rpx;
	justify-items: center;
	align-items: center;
	image{
		width: 750rpx;
		// height: 500rpx;
	}
	}
	.box{
		border: 1rpx solid #333;
		width: 750rpx;
		height: 200rpx;
		display: flex;
		flex-direction: column;
		.result{
			padding-top: 10rpx;
			font-size: 40rpx;
			font-weight: bold;
			color: #333;
		.content{
			font-size: 20rpx;
			
		}
	}
}
// .pic{
// 	height: 500rpx;
// 	width: 750rpx;
// }
</style>