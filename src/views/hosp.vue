<template>
  <div class="shopping-login">
    <div class="box">
      <div class="sbox">
        <div class="login-methods">
          <button class="login-btn" id="phoneLoginBtn" @click="showPhoneLogin" v-show="!isPhoneLoginVisible">← 手机验证码登录</button>
          <button class="login-btn" id="thirdPartyLoginBtn" @click="showThirdPartyLogin" v-show="!isThirdPartyLoginVisible">第三方登录 →</button>
        </div>
        <div v-show="isPhoneLoginVisible" class="phone-login">
          <div class="phone-input">
            <input v-model="phone" class="input" type="tel" placeholder="请输入手机号">
          </div>
          <div class="code-input">
            <input v-model="code" class="input" type="text" placeholder="请输入验证码">
            <button class="code-btn">获取验证码</button>
          </div>
        </div>
        <div v-show="isThirdPartyLoginVisible" class="third-party-login">
          <div class="login-methods1">
            <button class="login-btn1">
              <img src="../assets/R.jpg" alt="Wechat" class="icon">
              微信登录
            </button>
            <button class="login-btn1">
              <img src="../assets/OIP.jpg" alt="QQ" class="icon">
              QQ登录
            </button>
          </div>
        </div>
        <div>
          <div v-if="showPopup" class="popup">
            <p v-if="loginSuccess" class="success-message">登录成功！</p>
            <p v-if="loginFailed" class="error-message">登录失败，请检查手机号和验证码是否正确。</p>
          </div>
          <button class="log" @click="simulateLogin">登录</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      phone: '',
      code: '',
      isPhoneLoginVisible: true,
      isThirdPartyLoginVisible: false,
      loginSuccess: false,
      loginFailed: false,
      showPopup: false, 
    };
  },
  methods: {
    showPhoneLogin() {
      this.isPhoneLoginVisible = true;
      this.isThirdPartyLoginVisible = false;
    },
    showThirdPartyLogin() {
      this.isPhoneLoginVisible = false;
      this.isThirdPartyLoginVisible = true;
    },
    simulateLogin() {
      // 模拟登录验证，这里只检查手机号和验证码是否符合要求
      if (this.phone === '123456789' && this.code === '1234') {
        this.loginSuccess = true;
        this.loginFailed = false;
      } else {
        this.loginSuccess = false;
        this.loginFailed = true;
      }
      this.showPopup = true; // 登录后显示弹窗
    },
  },
};
</script>

<style scoped>
.shopping-login {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box {
  width: 450px;
  height: 800px;
  overflow-y: hidden;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  background: url('../assets/1.jpg'); 
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
}

.sbox {
  width: 350px;
  height: 300px;
  background: rgba(255, 255, 255, 0.9);
  padding: 20px;
  border-radius: 10px;
  text-align: center;
}

.login-methods {
  margin-bottom: 15px;
  display: flex;
  justify-content: center;
}

.login-btn {
  display: inline-block;
  padding: 10px 30px;
  font-size: 14px;
  font-weight: bold;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-align: center;
  background-color: #5df84f;
  margin: 0 20px;
}

.phone-login,
.third-party-login {
  margin-top: 20px;
}

.input {
  width: calc(100% - 20px);
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
  margin: 10px;
}

.code-btn {
  width: 120px;
  height: 36px;
  background-color: #5df84f;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.code-input {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.login-btn1 {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 10px 20px;
  margin: 10px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff;
  cursor: pointer;
}

.icon {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}

.log {
  width: 200px;
  height: 40px;
  margin-top: 40px;
  background: #5df84f;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.success-message {
  color: green;
  margin-top: 10px;
}

.error-message {
  color: red;
  margin-top: 10px;
}

.popup {
  position: fixed;
  top: 50px;
  left: 50%;
  transform: translateX(-50%);
  width: 300px;
  padding: 10px;
  background-color: rgba(255, 255, 255, 0.9);
  border: 1px solid #ccc;
  border-radius: 5px;
  text-align: center;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.success-message,
.error-message {
  margin: 5px 0;
}


 /*当屏幕宽度小于或等于 768 像素时，应用这里面的样式。*/
@media only screen and (max-width: 768px) {
  .box {
    width: 90%;
    max-height: 90vh;
  }

  .sbox {
    width: 100%;
    height: auto;
  }

  .log {
    width: 100%;
  }
}
</style>





