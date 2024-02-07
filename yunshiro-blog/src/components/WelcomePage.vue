<template>
  <!-- profile 部分 -->
  <div class="profile">
    <img :class= "{rotoPlay: isPlay, rotoStop: isStop}" class="initState" src="../assets/welcomepage-profile.jpg" alt="profile" @click="playMusic">
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

  <!-- 播放背景音乐 -->

  <audio ref="audio" src="http://music.163.com/song/media/outer/url?id=1926603905.mp3" autoplay loop></audio>


</template>

<script setup lang="ts" name="WelcomePage">
  import { ref } from 'vue'

  let audio = ref()
  let played = 0

  const isPlay = ref(false)
  const isStop = ref(true)
  const isConti = ref(false)


  // 播放音乐同时让profile旋转
  function playMusic() {
    if (played === 0) {
      audio.value.play()
      played = 1
      isPlay.value = true
      isStop.value = false
    } else if (played === 1) {
      audio.value.pause()
      isStop.value = true
      isPlay.value = false
      played = 0
    }
  }
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
  
  border-radius: 50%;
  box-shadow: 0 0 15px rgb(238, 197, 204);
}

.profile img {
  border-radius: 60%;
}

/* main 部分样式 */
.main h1 {
  text-align: center;
  color: white;
  font-family: 'Pacifico';
  text-shadow: 0 0 3px rgb(219, 107, 107);
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

.main nav li a {
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
footer div span {
  font-family: 'Pacifico';
  font-size: 6px;
  color: beige;
  text-shadow: 0 0 3px;
}

/* 播放背景music */

/* 旋转 */
.initState {
  animation: rotoImg 10s linear infinite;
}
.rotoPlay {
  animation-play-state: running;
}

.rotoStop {
  animation-play-state: paused;
}


@keyframes rotoImg {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}
</style>