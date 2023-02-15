<template>
  <footer class="footer">
    <div class="footer__top">
      <div class="footer__item first">
        <div class="footer__logo">
          <img src="/img/bbsoft-logo.png" alt="bbsoft-logo" class="image" />
        </div>
        <router-link to="/agreements" class="user-agr__link">
          <span class="yellow-gradient">USER </span>
          <span class="gray-gradient">AGREEMENT</span>
        </router-link>
      </div>
      <div class="footer__item third">
        <span class="gray-gradient"> MADE WITH </span>
        <span class="yellow-gradient">BB </span
        ><span class="gray-gradient">FOR GAMEFI</span>
      </div>
    </div>
    <div class="footer__item first media">
      <div class="footer__logo">
        <img src="/img/bbsoft-logo.png" alt="bbsoft-logo" class="image" />
      </div>
      <router-link to="/agreements" class="user-agr__link">
        <span class="yellow-gradient">USER </span>
        <span class="gray-gradient">AGREEMENT</span>
      </router-link>
    </div>
    <div class="footer__item second">
      <div class="footer-col-item">
        <a class="disabled" href="">BBPLACE (Coming Soon)</a>
        <a href="" class="disabled">BBAPP (Coming Soon)</a>
        <a target="_blank" href="https://bbdex.io">BBDEX</a>
      </div>
      <div class="footer-col-item">
        <a target="_blank" href="https://moovy.io/">MOOVY</a>
        <a target="_blank" href="https://twitter.com/bbsoft_io">TWITTER</a>
        <a target="_blank" href="https://instagram.com/bbsoft_io">INSTAGRAM</a>
      </div>
    </div>
    <div class="footer__item third media">
      <span class="gray-gradient"> MADE WITH </span>
      <span class="yellow-gradient">BB </span
      ><span class="gray-gradient">FOR GAMEFI</span>
    </div>
  </footer>
</template>
<script setup></script>
<style scoped>
.footer {
  position: relative;
  bottom: 0;
  left: 0;
  padding: 20px 67px;
  z-index: 1;
  font-family: 'Inter', sans-serif;
  width: 100%;
  box-sizing: border-box;
  margin-top: 100px;
}
.footer__top {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 30px;
}
.footer__logo {
  width: 62px;
  margin-bottom: 20px;
}
.user-agr__link span {
  font-weight: 900;
  font-size: 14px;
  line-height: 12px;
}
.footer__item.second {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.footer__item.second a {
  font-weight: 900;
  font-size: 12px;
  line-height: 1.25;
  height: fit-content;
  margin-bottom: 10px;
  padding: 0 10px;
  color: #888686;
}
.footer__item.second a.disabled {
  pointer-events: none;
}
.footer__item.second a:not(:last-child) {
  margin-right: 67px;
}
.footer__item.third {
  height: fit-content;
  /* margin-bottom: 40px; */
  font-weight: 800;
  font-size: 14px;
  line-height: 1.25;
  width: fit-content;
}
.footer__item.first.media {
  display: none;
}
.footer__item.third.media {
  display: none;
}
.footer-col-item:not(:last-child) {
  margin-right: 67px;
}
@media (max-width: 1400px) {
  .footer {
    padding: 20px 40px;
  }
  .footer__item.second a:not(:last-child) {
    margin-right: 40px;
  }
  .footer-col-item:not(:last-child) {
    margin-right: 40px;
  }
}
@media (max-width: 1200px) {
  .footer {
    padding: 20px;
  }
  .footer__item.second a:not(:last-child) {
    margin-right: 20px;
  }
  .footer-col-item:not(:last-child) {
    margin-right: 20px;
  }
}
@media (max-width: 768px) {
  .footer__top {
    display: none;
  }
  .footer__item.first.media {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 40px;
  }
  .footer__item.third.media {
    display: block;
    margin: 0 auto;
    margin-top: 40px;
  }
  .footer-col-item {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-bottom: -20px;
  }
  .footer__item.second a {
    margin-bottom: 20px;
  }
}
@media (max-width: 556px) {
  .footer-col-item:not(:last-child) {
    margin-right: 0px;
  }
  .footer {
    padding: 20px 0;
  }
}
</style>
