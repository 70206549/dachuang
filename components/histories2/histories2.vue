<template>
	<view>
		<view class="content">
			<view class="row" v-for="item in 4">
				<view class="contentbox" @click="">
					<view class="pic">
						<image src="https://shuguo888.top/image/玉米1.jpg" mode="aspectFill"></image>
					</view>
					<view class="texts">
						<view class="title">
							疾病名称
						</view>
						<view class="info">
							疾病详细情况详细情况疾病详细情细情况
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"histories2",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.content{
		padding:20rpx 30rpx;
		.row{
			border-bottom: 1rpx dotted #efefef;
			padding: 20rpx 0;
			.contentbox{
				display: flex;
				
				.pic{
					width: 230rpx;
					height: 160rpx;
					padding-right: 10rpx;
					image{
						width: 100%;
						height: 100%;
					}
				}
				.texts{
					border-radius: 5%;
					background: #e0f9e1;
					flex: 1;
					padding-left: 20rpx;
					display: flex;
					flex-direction: column;
					justify-content: space-between;
					.title{
						font-size: 40rpx;
						color: #000;
					}
					.info{
						font-size: 35rpx;
						color: #555;
						text-overflow: -o-ellipsis-lastline;
						overflow: hidden;				
						text-overflow: ellipsis;
						display: -webkit-box;			
						-webkit-line-clamp: 2;			
						line-clamp: 2;					
						-webkit-box-orient: vertical;	

					}
				}
			}
		}
	}
</style>