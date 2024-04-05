<template>
    <div class="shopping-login">
        <div class="box">
            <div class="sbox">
                <div class="login-methods">  
                    <button class="login-btn" id="phoneLoginBtn" @click="showPhoneLogin" style="margin: 20px;">手机验证码登录</button>  
                    <button class="login-btn" id="thirdPartyLoginBtn" @click="showThirdPartyLogin" style="margin: 20px;">第三方登录</button>
  
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
                        <button class="login-btn1" >
                          <img src="../assets/OIP.jpg" alt="QQ" class="icon">
                          QQ登录
                        </button>
                        <!-- <button class="login-btn" @click="loginWithWeibo">
                          <img src="../assets/先不做了" alt="Weibo" class="icon">
                          微博登录
                        </button> -->
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
    // *v-show 指令来根据条件控制元素的显示与隐藏。*//
</script>



<style>
.shopping-login{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}   

.login-methods {  
  margin-bottom: 15px;
  display: flex;
  justify-content: center; 
  /* box-shadow: 0 0 10px rgba(151, 142, 142, 0.2); */
} 

.box{
    width: 450px;
    height: 800px;
    /* background: rgba(255, 255, 255, 0.9); */
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    background: url('../assets/1.jpg');
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
}
.sbox{
    width: 350px;
    height: 300px;
    background: rgba(255, 255, 255, 0.9);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(151, 142, 142, 0.2);
    text-align: center;

  }

.phone-login{
    width: 350px;
    height: 100px;
    /* box-shadow: 0 0 10px rgba(151, 142, 142, 0.2); */
    text-align: center;
}

.log{
    width: 200px;
    height: 40px;
    margin: 40px 0 0 0 ;
    background: #5df84f;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}


.input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-sizing: border-box;
    margin: 10px;
  }

.code-btn {
  width: 150px;
  height: 36px;
  background-color: #5df84f;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin-left: 10px;
}

.code-input{
  display: flex;  
  align-items: center; 
}

.login-btn{
    display: inline-block;  
    padding: 10px 30px;
    font-size: 10px; 
    font-weight: bold; 
    color: #000000; 
    border: none; 
    border-radius: 5px; 
    cursor: pointer; 
    text-align: center; 
    background-color: darkgray;  
}

.third-party-login {
  text-align: center;
}

.login-methods1 {
  margin-top: 20px;
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


  </style>