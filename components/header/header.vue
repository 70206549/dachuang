<template>
	<view class="hoc-user-panel-sgm" @click="handleClick">
		<image class="hoc-user-panel-sgm_bg" src="http://ae8b3ee28597856d3283.qiniucdn.apicloud-system.com/apicloud/4ab30505532e709b72bc49fde2ff3b2b.png"></image>
		<view class="hoc-user-panel-sgm-wrap">
			<img class="hoc-user-panel-sgm-logo" :src="avatar" mode="aspectFill"/>
			<text class="hoc-user-panel-sgm-name">{{nickname}}</text>
			<image class="hoc-user-panel-sgm-gol" src="http://ae8b3ee28597856d3283.qiniucdn.apicloud-system.com/apicloud/7158c8c5425bd78b31d74da4ca8563f2.png"></image>
		</view>
	</view>
</template>
<script>
export default {
	name: 'header',
	apiready() {//like created

	},
	data() {
		return {
			id: this.props.id !== undefined ? this.props.id : '111',
            avatar: this.props.avatar !== undefined ? this.props.avatar : "http://aea8bc2ccdd582de43c1.qiniucdn.apicloud-system.com/apicloud/46e4b8d7a4a8d1febeec082516a8e8f5.png",
            nickname: this.props.nickname !== undefined ? this.props.nickname : "测试账号"
		}
	},
	methods: {
		handleClick() {
			this.fire('handleClick')
		}
	}
}
</script>
<style>
.hoc-user-panel-sgm{
    height: 126px;
}
.hoc-user-panel-sgm_bg{
    position: absolute;
    width: 100%;
    height: 100%;
}
.hoc-user-panel-sgm-wrap{
	flex-direction: row;
	align-items: center;
    height: 100%;
}
.hoc-user-panel-sgm-logo{
    width: 60px;
    height: 60px;
    border-radius: 50%;
	margin-left: 20px;
	background-color: #f8f8f8;
}
.hoc-user-panel-sgm-name{
	flex: 1;
    font-size: 17px;
    color: white;
	margin: 0 15px;
}
.hoc-user-panel-sgm-gol{
    width: 16px;
    height: 16px;
    margin-right: 20px;
}
</style>