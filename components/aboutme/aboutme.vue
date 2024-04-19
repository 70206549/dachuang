<template>
	<view>
		<view class="header" @click="onLogin">
			<view class="srcs">
				<image src="/static/image/头像 女孩.png" mode=""></image>
			</view>
			
			<view class="text">
				<view class="please">请登录</view>
				<view class="tell">极真工作室出品</view>
			</view>
		</view>
		<view class="body">
			<view class="detail" v-for="(item,num) in navArr" :key="num">
				<view class="row">
					<view class="start">
						<image :src="scrArr[num]" mode="aspectFit"></image>
					</view>
					<view class="mid">{{item}}</view>
					<view class="end">
						<image src="/static/image/展开.png" mode="aspectFit"></image>
					</view>
				</view>
				
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		name:"aboutme",
		data() {
			return {
				navArr:[
					"识别记录",
					"查看消息",
					"清除缓存",
					"在线客服",
					"我的设置",
					"关于我们"
				],
				scrArr:[
					"/static/image/浏览记录.png",
					"/static/image/消息.png",
					"/static/image/清楚缓存.png",
					"/static/image/mine2.png",
					"/static/image/设置.png",
					"/static/image/关于我们.png"
				]
			};	
		},
		methods:{
			onLogin(){
				
			}
		}
	}
</script>

<style lang="scss">
	.header{
		height: 200rpx;
		width: 750rpx;
		background: #d6edf9 ;
		display: flex;
		// justify-content: center;
		padding-left: 40rpx;
		align-items: center;
		.srcs{image{
			height: 150rpx;
			width: 150rpx;
		}
		}
		.text{
			
			padding-left: 30rpx;
			.please{
				font-size: 48rpx;
				font-weight: bold;
			}
			.tell{
				font-size: 35rpx;
				// font-weight: bold;
			}
		}
		
	}
	.body{
		width: 750rpx;
		height: 600rpx;
		// background: papayawhip;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		.row{
			display: flex;
			flex: 6;
			height: 90rpx;
			border-bottom: 1rpx dotted #8a8a8a;
			// padding: 10rpx 0;
			border-radius: 5%;
			padding-bottom: 5rpx;
			justify-content: space-between;
			align-items: center;
			image{
				width: 50rpx;
				height: 50rpx;
				padding-left: 20rpx;
				padding-top: 10rpx;
			}
			.mid{ 
				padding-right: 410rpx;
				font-size: 40rpx;
				font-weight: bold;
				color: #555;
			}
		}
	}
</style>