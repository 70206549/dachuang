<template>
	<view>
		<view v-if="!item.queryTime">
			<view class="content">
				<!-- <view class="row" v-for="items in item.detailArr"></view> -->
					<view class="contentbox" @click="">
						<view class="pic">
							<image :src="item.item.img_url" mode="aspectFill"></image>
						</view>
						<view class="texts">
							<view class="title">
								{{item.item.classname}}
							</view>
							<view class="info" v-if="!item.queryTime">
								{{item.item.symptom}}
							</view>
							<view class="info" v-else>{{item.times}}</view>
						</view>
					</view>
			</view>
		</view>
		<view v-else>
			<view class="content">
					<view class="contentbox" @click="">
						<view class="pic">
							<image :src="item.item.picurl" mode="aspectFill"></image>
						</view>
						<view class="texts">
							<view class="title">
								{{item.item.title}}
							</view>
							<view class="info" v-if="!item.queryTime">
								{{item.symptom}}
							</view>
							<view class="info" v-else>{{item.item.times}}</view>
						</view>
					</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"content3",
		props:{
			item:{
				type:Object,
				default(){
					return {
						img_url:"https://shuguo888.top/image/R-C.jpg",
						classname:"组件默认标题",
						symptom:"详情",
						times:"0000-00-00 00:00:00",
						queryTime:"2023-01-01 00:00:00"
					}
				}
			}
		},
		
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.content{
		padding:20rpx 30rpx;
		
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
					background: #e5fafa;
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
</style>