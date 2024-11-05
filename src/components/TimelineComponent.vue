<template>
  <div class="timeline">
    <div class="cont left-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Alphabet inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="left-container-arrow"></span>
    </div>
    <div class="cont right-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Tesla inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="right-container-arrow"></span>
    </div>
    <div class="cont left-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Apple inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="left-container-arrow"></span>
    </div>
    <div class="cont right-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Amazon inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="right-container-arrow"></span>
    </div>
    <div class="cont left-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Apple inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="left-container-arrow"></span>
    </div>
    <div class="cont right-container">
      <img class="rounded-full" :src="univ" />
      <div class="text-box">
        <h2>Amazon inc.</h2>
        <small>2020</small>
        <p>Lorem ipsum</p>
      </div>
      <span class="right-container-arrow"></span>
    </div>
  </div>
</template>

<script>
import uni from "@/assets/uni.jpg";

export default {
  data() {
    return {
      univ: uni,
    };
  },
};
</script>

<style scoped>
.timeline {
  position: relative;
  width: 100%;
}

.cont {
  padding: 20px 50px;
  position: relative;
  width: 50%;
  animation: movedown 2s ease-in-out forwards;
  z-index: 9;
  opacity: 0;
  top: 5%;
}

@keyframes movedown {
  0% {
    opacity: 0.1;
    transform: translateY(-30px);
  }
  50% {
    opacity: 0.8;
  }

  100% {
    opacity: 1;
    transform: translateY();
  }
}

.text-box {
  color: #000 ;

  padding: 20px 30px;

  position: relative;
  border-style: solid;
  border-color: #000;
  border-width: 2px;
  border-radius: 6px;
  font-size: 15px;
}

.left-container {
  left: 0;
}
.right-container {
  left: 50%;
}

.cont img {
  position: absolute;
  width: 40px;
  /* border-radius: 50%; */
  right: -20px;
  top: 32px;
  z-index: 10;
}

.right-container img {
  left: -20px;
}

.timeline::after {
  content: "";
  position: absolute;
  width: 3px;
  height: 100%;
  background: #000;
  top: 0;
  left: 50%;
  margin-left: -1.5px;
  z-index: 1;
  animation: moveline 6s ease-in-out forwards;
}

@keyframes moveline {
  0% {
    opacity: 0;
    height: 0;
  }
  50% {
    opacity: 0.8;
  }
  100% {
    height: 100%;
  }
}

.cont:nth-child(2) {
  animation-delay: 0.5s;
}

.cont:nth-child(3) {
  animation-delay: 1s;
}

.cont:nth-child(4) {
  animation-delay: 1.5s;
}

.cont:nth-child(5) {
  animation-delay: 2s;
}

.cont:nth-child(6) {
  animation-delay: 2.5s;
}

.text-box h2 {
  font-weight: 600;
}

.text-box small {
  display: inline-block;
  margin-bottom: 15px;
}

.left-container-arrow {
  height: 0;
  width: 0;
  position: absolute;
  top: 35px;
  z-index: 2;
  border-top: 15px solid transparent;
  border-bottom: 15px solid transparent;
  border-left: 15px solid #000 ;
  right: 35px;
}
.right-container-arrow {
  height: 0;
  width: 0;
  position: absolute;
  top: 35px;
  z-index: 2;
  border-top: 15px solid transparent;
  border-bottom: 15px solid transparent;
  border-right: 15px solid #000 ;
  left: 35px;
}

@media screen and (max-width: 600px) {
  .timeline {
    margin: 10px auto;
  }
  .timeline::after {
    left: 31px;
  }
  .cont {
    width: 100%;
    padding-left: 80px;
    padding-right: 25px;
  }

  .text-box {
    font-size: 13px;
  }
  .text-box small {
    margin-bottom: 10px;
  }

  .right-container {
    left: 0;
  }

  .left-container img,
  .right-container img {
    left: 10px;
  }

  .left-container-arrow,
  .right-container-arrow {
    border-right: 15px solid #000 ;
    border-left: 0 solid #000;
    left: 67px;
    z-index: 8;
  }
}
</style>
