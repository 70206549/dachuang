<template>
    <view class="container">
		<view class="center">
			<image src="https://shuguo888.top/image/001.jfif" mode="aspectFill"></image>
		</view>
			<view class="login-container">
			  <form class="login-form" @submit.prevent="handleSubmit">
			    <view class="login-title">用户登录</view>
			    <view class="form-item">
			      <view class="input-label">
					  <image src="https://shuguo888.top/image/电话 (1).png" mode="aspectFill"></image>
				  </view>
			      <input type="number" v-model="username" placeholder="请输入手机号" />
			    </view>
			    <view class="form-item">
			      <view class="input-label">
					  <image src="https://shuguo888.top/image/锁 (1).png" mode="aspectFill"></image>
				  </view>
			      <input type="password" v-model="password" placeholder="请输入密码" />
				  
			    </view>
			    <view class="form-item">
					<button @click="postlogin" type="primary" class="login-btn" :disabled="!username || !password">登录</button>
			    </view>
			  </form>
			</view>
		<view class="bottons"></view>
</view>
</template>

<script>
export default {
	name:"login",
	data() {
		return {
		  username: '',
		  password: ''
		}
	  },
	methods: {
		handleSubmit() {
		},
		postlogin() {
			if (this.username==='15778586035'&&this.password==='123456789'){ 
				this.saveHistory()
				this.$emit("info",0)
			}else{
				uni.showToast({
					title: "账号或密码错误",
					icon:'error',
					duration: 1000
				})
			}
		},
		saveHistory(){
			
			let item={
				title:"极真",
				picurl:"/static/image/apple.png",
			}
			uni.setStorageSync("userdata",item)
		}
	  }
}
</script>

<style lang="scss">
.container {

	  .center{
		height: 300rpx;
		width: 100%;
		// padding:300rpx 0;  
		// background: #c4f6e0;
		border: 0 solid #ccc;
		image{
			height: 100%;
			width: 100%;
		}
	  }
	  
	  .login-container {
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100%;
			width: 100%;
			// background: #ccc;
			.login-form {
				  width: 100%;
				  padding: 10px;
				  border:1rpx solid #c4f6e0;
				  // border-radius: 8px;
				  // background-color: #fff;
				  .login-title {
				    font-size: 40rpx;
				    font-weight: bold;
				    margin-bottom: 20rpx;
				    text-align: center;
				  };
				  .form-item {
				  	  margin-bottom: 20rpx;
				  	  display: flex;
					  align-content: center;
					  justify-content: center;
				  	  .input-label {
						  padding: 1rpx 10rpx;
							image{
							width: 50rpx;
							height: 50rpx;
							}
				  	  };
				  	  input {
				  	      border: 1rpx solid #ccc;
				  	      height: 60rpx;
						  width: 500rpx;
						  padding:0 10rpx
				  	  };
				  	  .login-btn {
				  	    width: 580rpx;
						color: #fff;
				  	  }
				  }
			};
			
	  }
	  // .bottons{
		 //  background-color: #85d5fa;
		 //  width: 100%;
		 //  height: 500rpx;
	  // }
}
</style>
