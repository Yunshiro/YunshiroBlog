<template>
  
  <!-- profile 部分 -->
  <div class="profile">
    <img src="../assets/welcomepage-profile.jpg" alt="profile">
  </div>
  
  <!-- 导航栏等部分 -->
  <div class="main">
    <h1>Hello! Wellcome to YunshiroBlog!</h1>
    <hr>
    <p>I am crazy in coding!!!</p>
    <nav>
      <li><a href="#">文章</a></li>
      <li><a href="#">壁纸精选</a></li>
      <li><a href="#">代办清单</a></li>
      <li><a href="#">关于作者</a></li>
    </nav>
  </div>

  <!-- 毛玻璃效果 -->
  <div class="blur-panel">

  </div>
  
  <!-- footer 部分 -->
  <footer>
    <!-- 后续修改 -->
    <div>
      <span>© 2024 YunshiroBlog.love</span>
    </div>
  </footer>
  
</template>

<script setup lang="ts" name="WelcomePage">
  
</script>


<style>
  /* 背景图 */
  html {
    background-image: url('../assets/background.png');
    background-repeat: no-repeat;
    background-size: cover;
  }

  /* 欢迎页profile样式 */
  .profile {
    height: 220px;
    width: 220px;
    display: flex;
    margin: auto;
    margin-top: 40px;

    box-shadow: 0 0 3px;
  }
  
  /* main 部分样式 */
  .main h1 {
    text-align: center;
    color: white;
    font-family: 'Pacifico';
    text-shadow: 0 0 3px;
  }

  .main hr {
    width: 70%;
    margin: auto;
    border: 1px solid;
    color: rgba(0, 255, 255, 0.74);
  }

  .main p {
    text-align: center;
    font-size: 9px;
    padding-bottom: 50px;
    color: white;
    font-family: 'Pacifico', serif;
  }

  .main nav {
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 300px;
    font-family: 'Zcool', serif;
  }


  .main nav li {
    margin-bottom: 40px;
    padding-top: 10px;
  }

  .main nav li a{
    display: block;
    text-decoration: none;
    font-size: 24px;
    width: 200px;
    text-align: center;
    color: rgb(102, 250, 213);
    font-weight: 19px;

  }

  .main nav li a:hover {
    background-color: rgb(245, 245, 245);
    border-radius: 5px;
  }

  .main nav li a:active {
    color: rgb(214, 112, 112);
  }

  /* 毛玻璃效果 */
  .blur-panel {
    position: relative;
    top: -303px;
    margin: auto;
    height: 300px;
    width: 300px;
    
    background: rgba(255, 255, 255, 0.2);
    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(8px);
    box-shadow: 0 0 10px;
    border-radius: 15px;
    z-index: -1;
  }


  /* footer 样式 */
  footer div span{
    font-family: 'Pacifico';
    font-size: 6px;
    color: beige;
    text-shadow: 0 0 3px;
  }
</style>