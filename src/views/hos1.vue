<template>
    <div class="box">
      <div class="pu"></div>
      <div class="welcome">欢迎点餐</div>
      <div class="welcome1">点餐前请先注册，如有账号直接点击登录按钮登录</div>
      <button class="create" @click="toggleCreateBox(true)">创建账号</button>
      <button class="log" @click="toggleLoginBox(true)">登录</button>
      <div class="sm">By logging in or registering, you have agreed to the Terms and Conditions and Privacy Policy.</div>
      <div class="overlay" v-if="showCreateBox || showLoginBox" @click="toggleCreateBox(false); toggleLoginBox(false)"></div> <!-- 灰色遮罩层 点击登录弹出登录框 背景变灰 -->
      <div class="create-box" v-if="showCreateBox">  
        <!-- 创建账号框的内容 -->  
        <h2>创建账号</h2>  
        <form>
          <input type="text" placeholder="用户名" required>
          <input type="email" placeholder="邮箱" required>
          <input type="password" placeholder="密码" required>
          <button type="submit" @click.prevent="createAccount">注册</button>
        </form>
      </div> 
      <div class="login-box" v-if="showLoginBox">  
        <!-- 登录框的内容 -->  
        <h2>登录</h2>  
        <form>
          <input type="text" placeholder="用户名" required>
          <input type="password" placeholder="密码" required>
          <button type="submit" @click.prevent="login">登录</button>
        </form>
      </div> 
    </div>
  </template>
  
  <script>
  export default {  
    data() {
      return {
        showCreateBox: false,
        showLoginBox: false
      };
    },
    methods: {  
      toggleCreateBox(show) {  
        this.showCreateBox = show;  
      },
      toggleLoginBox(show) {  
        this.showLoginBox = show;  
      },
      createAccount() {
        console.log('注册按钮被点击了');
      },
      login() {
        console.log('登录按钮被点击了');
      }
    }  
  }  
  </script>
  
  <style>
  .box {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative; /* 添加相对定位 */
  }
  
  .pu {
    width: 80%;
    height: 25%;
    margin-top: 38%;
    box-sizing: border-box;
    background: url('../assets/2.png') no-repeat;
    background-size: contain;
    background-position: center;
  }
  
  .welcome {
    width: 100%;
    height: 5%;
    margin-top: 10%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 30px;
  }
  
  .welcome1 {
    width: 60%;
    height: 5%;
    margin-top: 8%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 15px;
    color: #646464;
  }
  
  .create, .log {
    width: 80%;
    height: 53px;
    margin-top: 10px;
    background: #32B768;
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    font-size: 15px;
  }
  
  .sm {
    width: 60%;
    height: 5%;
    margin-top: 3%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 10px;
    color: #646464;
  }
  
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6); /* 半透明黑色背景 */
    z-index: 998; /* 低于登录框 */
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .create-box, .login-box {
    position: fixed; /* 调整为固定定位 */
    bottom: 0; /* 显示在底部 */
    left: 0; /* 从左边开始 */
    width: 100%;
    background-color: white; 
    padding: 20px;
    box-sizing: border-box;
    transition: bottom 0.3s ease-in-out;
    z-index: 999;
    transform: translateY(-85%); 
  }
  
  .login-box.visible {
    bottom: 0;
  }
  
  input, button {
    margin: 10px 0;
    width: calc(100% - 20px);
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-sizing: border-box;
  }
  
  button {
    background-color: #32B768;
    color: white;
    cursor: pointer;
  }
  
  .log{
    background-color: #D1FAE5;
    color: #10B981;
    cursor: pointer;
  }
  
  .register-link {
  margin-top: 10px;
  text-align: center;
  color: white;
}

.register-link a {
  color: #D1FAE5;
  text-decoration: underline;
}
</style>