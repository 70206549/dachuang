<template>
    <view class="container">
        <view class="register-container">
          <form class="register-form" @submit.prevent="handleSubmit">
            <view class="register-title">用户注册</view>
            <view class="form-item">
              <view class="input-label">手机号</view>
              <input type="tel" v-model="phone" placeholder="请输入手机号" />
            </view>
            <view class="form-item">
              <view class="input-label">设置密码</view>
              <input type="password" v-model="password" placeholder="请输入密码" />
            </view>
            <view class="form-item">
              <view class="input-label">确认密码</view>
              <input type="password" v-model="password2" placeholder="再次输入密码" />
            </view>
            <view class="form-item">
              <view class="input-label">验证码</view>
              <view class="code-input">
                  <input type="number" v-model="code" placeholder="请输入验证码" />
                  <button type="primary" class="code-btn" :disabled="!phone || sending" @click="handleSendCode">{{ sending ? `${seconds}秒后重试` : '获取验证码' }}</button>
              </view>
            </view>
            <view class="form-item">
              <button type="primary" class="register-btn" :disabled="!phone || !code || !password || !password2">注册</button>
            </view>
          </form>
        </view>
    </view>
</template>

<script>
export default {
	name:"registe",
	  data() {
		return {
		  phone: '',
		  code: '',
		  password: '',
		  password2:'',
		  sending: false, // 是否正在发送验证码
		  seconds: 60, // 倒计时秒数
		  timer: null, // 倒计时计时器
		}
	  },
	  methods: {
		handleSubmit() {
		  // 处理注册逻辑
		},
		handleSendCode() {
		  // 发送验证码
		  this.sending = true;
		  this.timer = setInterval(() => {
			this.seconds--;
			if (this.seconds === 0) {
			  clearInterval(this.timer);
			  this.timer = null;
			  this.seconds = 60;
			  this.sending = false;
			}
		  }, 1000);
		},
	  },
}
</script>

<style>
.container {
  /* display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh; */
}
    
.register-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
}

.register-form {
  width: 580rpx;
  padding: 10px;
  /* border: 1px solid #ccc; */
  border-radius: 8px;
  background-color: #fff;
}
input {
    border: 1px solid #ccc;
    height: 35px;
}

.register-title {
  font-size: 48rpx;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: center;
}

.form-item {
    margin-bottom: 20px;
}

.input-label {
  display: block;
  font-size: 32rpx;
  font-weight: bold;
  margin-bottom: 15rpx;
}

.code-input {
  display: flex;
  align-items: center;
}

.code-input input {
  flex: 1;
  margin-right: 10rpx;
}

.code-btn {
  font-size: 28rpx;
  border: none;
  background-color: transparent;
  color: #fff;
  outline: none;
}

.register-btn {
  width: 580rpx;
  color: #fff;
}
</style>
