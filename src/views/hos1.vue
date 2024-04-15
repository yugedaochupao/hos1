<template>
    <div class="box">
        <div class="pu"></div>
        <div class="welcome">欢迎点餐</div>
        <div class="welcome1">点餐前请先注册，如有账号直接点击登录按钮登录</div>
        <button class="create" @click="showLoginBox('create')">创建账号</button>
        <button class="log" @click="showLoginBox('log')">登录</button>
        <div class="sm">By logging in or registering, you have agreed to the Terms and Conditions and Privacy Policy.</div>
        <div class="login-box" id="loginBox" v-if="showLoginBox">  
            <!-- 登录框的内容 -->  
            <h2>登录或注册</h2>  
            <!-- 表单、按钮等 -->  
        </div> 

    </div>

  </template>


  <script>  
    export default {  
        methods: {  
            showLoginBox(type) {  
                const loginBox = document.getElementById('loginBox');  
                if (loginBox.classList.contains('visible')) {  
                    // 如果登录框已经是可见的，则隐藏它  
                    loginBox.classList.remove('visible');  
                } else {  
                    // 否则显示登录框，并滚动到它  
                    loginBox.classList.add('visible');  
                    window.scrollTo({  
                        top: document.documentElement.scrollHeight / 2 - loginBox.offsetHeight / 2,  
                        behavior: 'smooth' // 平滑滚动效果  
                    });  
                }  
            }  
        }  
    }  
    </script>




  <style>
.box{
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.pu{
    width: 80%;
    height: 25%;
    margin-top: 38%;
    box-sizing: border-box;
    background: url('../assets/2.png') no-repeat;
    background-size: contain;
    background-position: center;
}

.welcome{
    width: 100%;
    height: 5%;
    margin-top: 10%;
    display: flex;  
    justify-content: center; 
    align-items: center; 
    font-weight: bold;
    font-size: 30px;

}
.welcome1{
    width: 60%;
    height: 5%;
    margin-top: 8%;
    display: flex;  
    justify-content: center; 
    align-items: center; 
    font-size: 15px;
    color: #646464;

}

.create{
    width: 80%;
    height: 53px;
    margin-top: 20%;
    background: #32B768;
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    font-size: 15px;

}

.log{
    width: 80%;
    height: 53px;
    margin-top: 10%;
    background: #D1FAE5;
    color: #10B981;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    font-size: 15px;
}

.sm{
    width: 60%;
    height: 5%;
    margin-top: 3%;
    display: flex;  
    justify-content: center; 
    align-items: center; 
    font-size: 10px;
    color: #646464;
}

.login-box {  
    position: fixed;  
    bottom: -100%;   
    width: 100%;  
    background-color: #535353;  
    padding: 20px;  
    box-sizing: border-box;  
    transition: bottom 0.3s ease-in-out; /* 平滑过渡效果 */  
    z-index: 999; /* 登录框在其他内容之上 */  
}  
  
.login-box.visible {  
    bottom: 50%; /* 显示时定位到屏幕一半 */  
    transform: translateY(50%); /* 调整位置，确保居中 */  
}




  </style>