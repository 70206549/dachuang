<template>
	<view>
		<view class="nav">
			<view class="items" :class="myindex==num ? 'active' : ''"
			v-for = "(item,num) in navArr" :key="num" @click="onnav(num)">
			<view class="item">{{item.title}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"selector",
		data() {
			return {
				navArr:[
					{title:"玉米"},
					{title:"甘蔗"},
					{title:"木薯"}
				],
				myindex:0
			};
		},
		methods:{
			onnav(e){
				console.log(e)
				this.myindex=e
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
			background: #e0f9e1;
			text-align: center;
			padding: 0 50rpx;
			border-radius: 10%;

			.item{
				font-size: 40rpx;
			}
			&.active{
				background: #82d7fa;
				color: #fff;
			}
		}
	}
</style>