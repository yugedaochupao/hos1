<template>
  <div class="box">
    <div class="pu">
      <div class="dropdown" style="position: absolute; top: 10px; left: 10px;">
        <button class="dropbtn">语言</button>
        <div class="dropdown-content">
          <a href="#">中文</a>
          <a href="#">English</a>
        </div>
      </div>
    </div>
    <div class="welcome">欢迎点餐</div>
    <div class="welcome1">点餐前请先注册，如有账号直接点击登录按钮登录</div>
    <button class="create" @click="toggleCreateBox(true)">创建账号</button>
    <button class="log" @click="toggleLoginBox(true)">登录</button>
    <div class="sm">By logging in or registering, you have agreed to the Terms and Conditions and Privacy Policy.</div>
    <div class="overlay" v-if="showCreateBox || showLoginBox" @click="toggleCreateBox(false); toggleLoginBox(false)"></div>
    <div class="create-box" v-if="showCreateBox">  
      <h2>创建账号</h2>  
      <form>
        <input type="text" placeholder="用户名" required>
        <input type="email" placeholder="邮箱" required>
        <input type="password" placeholder="密码" required>
        <button type="submit" @click.prevent="createAccount">注册</button>
      </form>
    </div> 
    <div class="login-box" v-if="showLoginBox">  
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
  position: relative;
}

.pu {
  width: 80%;
  height: 25%;
  margin-top: 38%;
  box-sizing: border-box;
  background: url('../assets/2.png') no-repeat;
  background-size: contain;
  background-position: center;
  position: relative;
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
  background-color: rgba(0, 0, 0, 0.6);
  z-index: 998;
  display: flex;
  justify-content: center;
  align-items: center;
}

.create-box, .login-box {
  position: fixed;
  bottom: 0;
  left: 0;
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

.dropdown {
  position: absolute;
  top: 10px;
  left: 10px;
}

.dropbtn {
  background-color: #32B768;
  color: white;
  padding: 10px;
  font-size: 15px;
  border: none;
  cursor: pointer;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 120px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 999;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #ddd;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #3e8e41;
}
</style>
