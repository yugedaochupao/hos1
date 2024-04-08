<template>
  <div class="shopping-login">
    <div class="box">
      <div class="sbox">
        <div class="login-methods">
          <button class="login-btn" id="phoneLoginBtn" @click="showPhoneLogin">手机验证码登录</button>
          <button class="login-btn" id="thirdPartyLoginBtn" @click="showThirdPartyLogin">第三方登录</button>
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
          <button class="log">登录</button>
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




