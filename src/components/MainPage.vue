<template>
  <section class="section main">
    <div class="main__logo">
      <img src="/img/bbsoft-logo.png" alt="bbsoft-logo" class="image" />
    </div>
    <div class="main__content">
      <h1 class="section-title">
        <span class="yellow-gradient">bbsoft</span> <br />
        <span class="white-gradient"> making web3 </span> <br />
        <span class="white-gradient">easier</span>
      </h1>
      <p class="text white main__text">
        We are creating a single ecosystem that will cover all the needs of the
        player in the world of Web3 games
      </p>
      <BaseButton
        value="Learn more"
        link="https://bbsoft-io.gitbook.io/bbsoft-ecosystem/intro/introduction"
      />
    </div>
    <div class="main-bg">
      <video preload="metadata" autoplay muted loop playsinline class="video">
        <source type="video/mp4" src="/video/main-bg.mp4" />
      </video>
      <div class="gradient-bottom"></div>
    </div>
  </section>
</template>
<script setup>
import { BaseButton } from '@/components';
</script>
<style scoped>
.section {
  padding-top: 40px;
  box-sizing: border-box;
  position: relative;
  min-height: 100vh;
}
.main__logo {
  margin: 0 0 0 80px;
  width: 204px;
  position: relative;
  z-index: 1;
  user-select: none;
  pointer-events: none;
}
.main__content {
  margin-left: 16.43vw;
  margin-top: 30px;
  position: relative;
  z-index: 1;
}
.main__text {
  max-width: 216px;
  margin: 30px 0 50px 0;
}
.main-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  background: #000;
}
@media (max-width: 1200px) {
  .main__content {
    margin-left: 16.43vw;
    margin-top: 0px;
    position: relative;
    z-index: 1;
  }
}
@media (max-width: 992px) {
  .section {
    background: #000;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 100vh;
  }
  .main-bg {
    height: 70%;
    z-index: 0;
  }
  .gradient-bottom {
    height: 200px;
    background: linear-gradient(to top, #000 15%, rgba(0, 0, 0, 0));
  }
  .main__content {
    margin-bottom: 150px;
  }
}
@media (max-width: 768px) {
  .section {
    padding-top: 0;
  }
  .main__content {
    margin-left: 40px;
    margin-bottom: 150px;
  }
  .main__logo {
    margin: 0 0 0 22px;
    width: 130px;
  }
  .main__text {
    max-width: 316px;
    margin: 30px 0 50px 0;
  }
  .main-bg {
    margin-top: 70px;
  }
}
@media (max-width: 556px) {
  .main-bg {
    height: 60%;
  }
  .main__content {
    margin-left: 40px;
    margin-bottom: 150px;
  }
  .main__logo {
    width: 74px;
  }
  .main__text {
    max-width: 216px;
    margin: 20px 0 30px 0;
  }
}
</style>
