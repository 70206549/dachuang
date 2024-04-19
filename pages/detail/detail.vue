<template>
	<view>
		<!-- <Onedetail :item="{item:objDetail}"></Onedetail> -->
		<Alldetail :item="{item:objDetail}"></Alldetail>
		<!-- <Alldetail :item="{item:objDetail}"></Alldetail> -->
	</view>
</template>

<script>
	import {parseTime} from "@/utils/tool.js"
	export default {
		data() {
				return {
					objDetail:null,
					option:null,
					myindex:0,
					classId:"",
					Arrdata:[]
				};
			},
			onLoad(e) {
				console.log(e)
				this.option=e
				this.getNavData()
				
			},
			methods:{
				getNavData(){
					let abc = this.classId;
					uni.request({
						url:"https://www.shuguo888.top/home/all_info",
						success: res => {
							this.objDetail=res.data.data[this.option.uid][this.option.id]
							// this.saveHistory()
							uni.setNavigationBarTitle({
								title:res.data.data[this.option.uid][this.option.id]["classname"]
							})
						}
					})
				},
				saveHistory(){
					let historyArr=uni.getStorageSync("historyArr") || []
					let item={
						uid:this.option.uid,
						id:this.option.id,
						title:this.objDetail["classname"],
						picurl:this.option['url'],
						times:parseTime(Date.now())
					}
					historyArr.unshift(item)
					// historyArr.
					uni.setStorageSync("historyArr",historyArr)
				}
			}
	}
</script>

<style lang="scss">

</style>
