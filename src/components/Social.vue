<template>
  <section class="section">
    <h2 class="section-title section-title_h2 yellow-gradient">by BBSoft</h2>
    <div class="social-bg">
      <div class="gradient-bottom"></div>
      <div class="gradient-left"></div>
      <div class="gradient-right"></div>
      <video preload="metadata" autoplay muted playsinline class="video">
        <source type="video/mp4" src="/video/moovy-bg.mp4" />
      </video>
    </div>
    <div class="social__content">
      <div class="social__buttons">
        <BlueButton value="Twitter" />
        <BlueButton value="Telegram" />
        <BlueButton value="Website" />
      </div>
      <div class="stores__buttons">
        <BlackButton value="AppStore" />
        <BlackButton value="Google Play" />
      </div>
      <p class="text white">
        Moovy is a drive2earn project that combines the best of both online
        gaming and social networks. It enables users to drive real-world cars,
        get rewarded in cryptocurrency, and meet new people while doing so.
      </p>
      <div class="social__subtitle blue-gradient section-subtitle moovy">
        DRIVE2EARN
        <div class="d-flex align-center">
          <div class="social__logo">
            <img src="/img/moovy-logo.svg" alt="moovy-logo" class="image" />
          </div>
          APP
        </div>
      </div>
    </div>
    <div class="gradient-top"></div>
    <div class="gradient-bottom"></div>
  </section>
</template>
<script setup>
  import { BlueButton, BlackButton } from '@/components';
</script>
<style scoped>
  .section {
    padding: 0 100px;
    position: relative;
    padding-top: 60px;
    overflow: hidden;
  }
  .section-title_h2 {
    margin-left: 60px;
    position: relative;
    z-index: 1;
  }
  .social__content {
    margin-top: 12%;
    position: relative;
    z-index: 1;
    max-width: 364px;
  }
  .social__buttons {
    display: flex;
  }
  .social__buttons a:not(:last-child) {
    margin-right: 20px;
  }
  .stores__buttons {
    width: 100%;
    display: flex;
    justify-content: space-between;
    margin-top: 40px;
    margin-bottom: 80px;
  }
  .stores__buttons a:not(:last-child) {
    margin-right: 30px;
  }
  .social-bg {
    position: absolute;
    top: 60%;
    transform: translateY(-50%);
    right: 0;
    width: 75%;
    /* height: 100%; */
    z-index: -1;
    background: #000;
  }
  .social__logo {
    width: 242px;
    margin-top: 5px;
    margin-right: 10px;
  }
  .section-subtitle {
    line-height: 1.25;
  }
  .moovy {
    margin-top: 20px;
  }
  .gradient-bottom {
    height: 100px;
  }
  .gradient-right {
    width: 50px;
  }
  @media (max-width: 992px) {
    .section {
      min-height: auto;
    }
    .social__logo {
      width: 180px;
    }
    .social__content {
      margin-top: 60px;
    }
    .stores__buttons {
      margin-top: 30px;
      margin-bottom: 40px;
    }
    .gradient-top {
      height: 250px;
    }
    .social-bg {
      top: 60%;
      width: 75%;
    }
  }
  @media (max-width: 768px) {
    .section {
      padding: 0 100px;
      padding-top: 100px;
    }
    .social-bg {
      position: relative;
      width: 100%;
      transform: scale(1.4);
      background: #000;
      margin-top: 80px;
    }
    .social__content {
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 auto;
    }
    .social__logo {
      width: 160px;
    }
    .section-title_h2 {
      margin: 0 auto;
      width: fit-content;
    }
  }
  @media (max-width: 556px) {
    .section {
      padding: 0 20px;
      padding-top: 100px;
    }
    .social-bg {
      transform: scale(1.5);
      margin-top: 100px;
    }
    .social__content {
      margin-top: 80px;
    }
    .gradient-bottom {
      height: 30px;
    }
    .gradient-top {
      height: 30px;
    }
    .gradient-left {
      width: 100px;
    }
    .social__content {
      max-width: 80vw;
    }
    .social__logo {
      width: 120px;
    }
  }
  @media (max-width: 400px) {
    .social__buttons a:not(:last-child) {
      margin-right: 10px;
    }
  }
</style>