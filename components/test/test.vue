<template>
	<view>
		<!-- <button @click="getNavData">test</button> -->
		<view class="" @click="getNavData">sdfgsdfgsdfgsdf{{navArr}}</view>
		
	</view>
</template>

<script>
	export default {
		name:"test",
		data() {
			return {
				navArr:[]
			};
		},
		onLoad(){
			this.getNavData();
		},
		onShow(){
			this.getNavData();
		},
		methods:{
			// test
			getNavData(){
				uni.request({
					url:"https://ku.qingnian8.com/dataApi/news/navlist.php",
					success: res => {
						console.log(res)
						this.navArr=res.data
					}
				})
			}
		},
		
		
	}
</script>

<style lang="scss">

</style>