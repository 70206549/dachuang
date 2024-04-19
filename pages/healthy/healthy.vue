<template>
	<view class="content">
		<view class="header">
			<image src="https://shuguo888.top/image/123.png" mode="aspectFit"></image>
		</view>
		<view class="body">
			农作物非常健康！！！
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

<style lang="scss">
	.content{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 750rpx;
		height:750rpx;
		.header{
		height: 500rpx;
		padding-bottom: 10rpx;
		}
		.body{
			background-color: #c8ebfa;
			font-size: 50rpx;
			text-align: center;
			border: 1rpx solid #ffffff;
			color: #2c1e1e;
		}
	}
	
</style>
