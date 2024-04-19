<template>
	<view>
		<view class="user">
			<view class="top">
				<image class="pic" src="https://shuguo888.top/image/浏览历史 (1).png" mode="aspectFill">
				</image>
				<view class="text">历史查询</view>
			</view>
			<view class="content"></view>
		</view>
		<view class="row" v-for="(item,num) in historyArrs" :key="num">
			<content3 :item="{item:item,queryTime:item.times}" @click.native="goDetail(item.uid,item.id,item.picurl)"></content3>
		</view>
		</view>
</template>

<script>
	export default {
		data() {
			return {
				navArr:[
					{title:"玉米"},
					{title:"甘蔗"},
					{title:"木薯"}
				],
				obj:[],
				detailArr:[],
				historyArrs:[],
				pic:"https://shuguo888.top/image/R-C.jpg",
				time:"0000-00-00 00:00:02",
				title:"历史标题",
				// detailArr:[0,1,2,3]
			};
		},
		onLoad() {
			this.getData()
		},
		methods:{
			goDetail(a,b,c){
				uni.navigateTo({
					url:`/pages/detail0/detail0?uid=${a}&id=${b}&url=${c}`
				})
			},
			getNavData(){
				uni.request({
					url:"https://www.shuguo888.top/home/all_info",
					success: res => {
						this.detailArr=res.data.data

					}
				})
			},
			getData(){
				this.historyArrs=uni.getStorageSync("historyArr") || []
			}
		}
		
	}
</script>

<style lang="scss">
	.user{
		.top{
			padding: 20rpx 0;
			background: #f8f8f8;
			color: #555;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			.pic{
				height: 130rpx;
				width: 130rpx;
			}
			.text{
				font-size: 35rpx;
				padding-top: 10rpx;
			}
		}
	}
</style>
