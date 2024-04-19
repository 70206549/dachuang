<template>
    <view class="container">
        <view class="login-container">
          <form class="login-form" @submit.prevent="handleSubmit">
            <view class="login-title">用户登录</view>
            <view class="form-item">
              <view class="input-label">手机号</view>
              <input type="text" v-model="username" placeholder="请输入手机号" />
            </view>
            <view class="form-item">
              <view class="input-label">密码</view>
              <input type="password" v-model="password" placeholder="请输入密码" />
            </view>
            <view class="form-item">
              <button type="primary" class="login-btn" :disabled="!username || !password">登录</button>
            </view>
          </form>
        </view>
    </view>
  
</template>

<script>
	export default {
		name:"my-login",
		data() {
			return {
				username: '',
				password: ''
			};
		},
		methods:{
			handleSubmit() {
			  // 处理登录逻辑
			}
		}
	}
</script>

<style lang="scss">
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh; /* 或者使用min-height: 100vh; */
}
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
}

.login-form {
  width: 100%;
  padding: 10px;
  /* border: 1px solid #ccc; */
  border-radius: 8px;
  background-color: #fff;
}
input {
    border: 1px solid #ccc;
    height: 35px;
}

.login-title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: center;
}

.form-item {
  margin-bottom: 20px;
}

.input-label {
  display: block;
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 8px;
}

.login-btn {
  width: 100%;
}
</style>