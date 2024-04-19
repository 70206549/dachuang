<template>
	<view class="alldata">

		<view class="nav">
			<view class="items" :class="myindex==num ? 'active' : ''"
			v-for = "(item,num) in navArr" :key="num" @click="onnav(num)">
			<view class="item">{{item.title}}</view>
			</view>
		</view>
		<view v-if="myindex==0">
			<view class="row" v-for="(item2,num2) in detailArr0" :key="num2">
				<content3 :item="{item:item2}" @click.native="goDetail(0,item2.id)"></content3>
			</view>
		</view>
		<view v-if="myindex==1">
			<view class="row" v-for="(item2,num2) in detailArr1" :key="num2">
				<content3 :item="{item:item2}" @click.native="goDetail(1,item2.id)"></content3>
			</view>
		</view>
		<view v-if="myindex==2">
			<view class="row" v-for="(item2,num2) in detailArr2" :key="num2">
				<content3 :item="{item:item2}" @click.native="goDetail(2,item2.id)"></content3>
			</view>
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
					classArr:["yumi","sugarcane","mushu"],
					idArr:["class_1","class_2","class_3","class_4","class_5"],
					obj:[],
					detailArr0:[],
					detailArr1:[],
					detailArr2:[],
					myindex:0
					
				};
			},
			onLoad() {
				this.getNavData()
			},
			onShow(){
				this.getNavData()
			},
			methods:{
				onnav(e){
					this.myindex=e
				}, 
				goDetail(a,b){
					b--
					uni.navigateTo({
						url:`/pages/detail/detail?uid=${this.classArr[a]}&id=${this.idArr[b]}`
					})
				},
				getNavData(){
					uni.request({
						url:"https://www.shuguo888.top/home/all_info",
						success: res => {
							this.detailArr0=res.data.data.yumi
							this.detailArr1=res.data.data.sugarcane
							this.detailArr2=res.data.data.mushu
	
						}
					})
				}
			}
			
	}
</script>

<style lang="scss">
	.nav{
		display: flex;
		justify-content: space-around;
		align-items: center;
		padding: 0 30rpx;
		.items {
			// flex: 3;
			line-height: 110rpx;
			background: #d1f9f8;
			text-align: center;
			padding: 0 50rpx;
			border-radius: 10%;

			.item{
				font-size: 40rpx;
			}
			&.active{
				background:#82d7fa;
				color: #fff;
			}
		}
	};
	.row{
		border-bottom: 1rpx dotted #efefef;
		padding: 10rpx 0;
		}
</style>
