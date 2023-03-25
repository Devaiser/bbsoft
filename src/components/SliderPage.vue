<template>
  <section class="section">
    <h2 class="section-title yellow-gradient slider-title">
      welcome to the <br />
      gate of gamefi
    </h2>

    <div class="slider-wrapper">
      <div class="slider-navigation">
        <div class="slider-button-prev">
          <img src="/img/slider-arrow.svg" alt="slider-arrow" />
        </div>
        <div class="slider-button-next">
          <img
            src="/img/slider-arrow.svg"
            alt="slider-arrow"
            class="rotate-180"
          />
        </div>
      </div>
      <div class="slider-pagination"></div>
      <Swiper
        :initial-slide="3"
        :speed="700"
        :pagination="paginationMedia"
        :modules="modules"
        :navigation="navigation"
        :breakpoints="breakpoints"
      >
        <SwiperSlide>
          <div class="slide-body">
            <div class="slide-image">
              <img src="/img/slider/place.png" alt="place" class="image" />
            </div>
            <div class="slide-content">
              <h3 class="section-subtitle yellow-gradient">
                Bbplace & bblaunch
              </h3>
              <p class="text big gray slider-text">
                Get first-hand access to game NFTs and other PFP projects
                through the BBPlace. Or participate in whitelist, INO, minting
                events on the exclusive BBLaunch
              </p>
              <div class="button-wrapper">
                <BaseButton value="Coming Soon" />
              </div>
            </div>
          </div>
        </SwiperSlide>
        <SwiperSlide>
          <div class="slide-body">
            <div class="slide-image">
              <img src="/img/slider/bbDex.png" alt="bbDex" class="image" />
            </div>
            <div class="slide-content">
              <h3 class="section-subtitle yellow-gradient">BBDex</h3>
              <p class="text big gray slider-text">
                Trade and manage a variety of digital assets precisely and
                intuitively. Swapping, staking, providing liquidity, and even
                accessing the bridge can be done right on your phone. Also gain
                access to exclusive game tokens on the proprietary DEX
              </p>
              <div class="button-wrapper">
                <BaseButton value="learn more" link="https://bbdex.io" />
              </div>
            </div>
          </div>
        </SwiperSlide>
        <SwiperSlide>
          <div class="slide-body">
            <div class="slide-image">
              <img
                src="/img/slider/walletToken.png"
                alt="walletToken"
                class="image"
              />
            </div>
            <div class="slide-content">
              <h3 class="section-subtitle yellow-gradient">
                super app for blockchain gaming
              </h3>
              <p class="text big gray slider-text">
                Access to the all BBSoft services and features right from your
                hand. Features include BBDex, BBID, BBPlace, BBLaunch, Swap and
                more!
              </p>
              <div class="button-wrapper">
                <BaseButton value="coming soon" />
              </div>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>
      <div class="slider-navigation media">
        <div class="slider-button-prev">
          <img src="/img/slider-arrow.svg" alt="slider-arrow" />
        </div>
        <div class="slider-pagination-media"></div>
        <div class="slider-button-next">
          <img
            src="/img/slider-arrow.svg"
            alt="slider-arrow"
            class="rotate-180"
          />
        </div>
      </div>
    </div>

    <div class="gradient-top"></div>
    <div class="gradient-bottom"></div>
    <div class="bg">
      <video preload="metadata" autoplay muted loop playsinline class="video">
        <source type="video/mp4" src="/video/bg.mp4" v-if="width > 556" />
        <source type="video/mp4" src="/video/media-bg.mp4" v-else />
        <img src="/img/bg.jpg" alt="bg" class="image" />
      </video>
    </div>
  </section>
</template>
<script setup>
import { ref } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { BaseButton } from '@/components';
import { Navigation, Pagination } from 'swiper';

import { useWindowSize } from '@vueuse/core';

import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

const { width } = useWindowSize();

const pagination = ref({
  el: '.slider-pagination',
  clickable: true,
});
const paginationMedia = ref({
  el: '.slider-pagination-media',
  clickable: true,
});

const breakpoints = {
  767: {
    pagination: pagination.value,
  },
};

const navigation = {
  nextEl: '.slider-button-next',
  prevEl: '.slider-button-prev',
};

const modules = [Navigation, Pagination];
</script>
<style scoped>
.section {
  position: relative;
  margin-top: 100px;
}
.slider-wrapper {
  margin-top: 50px;
  position: relative;
  z-index: 1;
}
.slider-title {
  text-align: center;
  position: relative;
  z-index: 1;
  padding: 0 40px;
  /* top: -60px; */
}
.slide-image {
  width: 45vw;
}
.slide-body {
  display: flex;
  align-items: center;
}
.slide-content {
  max-width: 32vw;
  margin-bottom: 60px;
  margin-left: 40px;
}
.slider-text {
  margin: 35px 0 52px 0;
}
.slider-pagination {
  z-index: 2;
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}
.slider-navigation.media {
  display: none;
}
.slider-navigation {
  display: flex;
  justify-content: flex-end;
  margin-right: 105px;
}
.slider-button-prev {
  margin-right: 30px;
  cursor: pointer;
}
.slider-button-next {
  cursor: pointer;
}
.slider-button-next,
.slider-button-prev {
  transition: all 0.3s ease 0s;
}
.swiper-button-disabled {
  opacity: 0.4;
  cursor: auto;
}
@media (max-width: 1200px) {
  .slide-content {
    max-width: 42vw;
  }
}
@media (max-width: 992px) {
  .section {
    min-height: auto;
    margin-top: 0px;
  }
}
@media (max-width: 768px) {
  .slider-navigation {
    display: none;
  }
  .slider-pagination-media {
    display: flex;
    justify-content: center;
    margin-right: 0;
    padding: 0 40px;
  }
  .slider-button-prev {
    margin-right: 0;
  }
  .slider-navigation.media {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 0;
    padding: 0 20px;
    width: fit-content;
    margin: 0 auto;
  }
  .slider-pagination {
    display: none;
  }
  .slide-body {
    flex-direction: column;
    text-align: center;
  }
  .slide-content {
    margin: 0;
    max-width: 70vw;
    margin-bottom: 40px;
  }
  .slide-image {
    width: 50vw;
  }
  .button-wrapper {
    display: flex;
    justify-content: center;
  }
}
@media (max-width: 556px) {
  .slide-image {
    width: 80vw;
  }
  .slide-content {
    max-width: 100vw;
    padding: 0 20px;
  }
  .slider-text {
    margin: 20px 0 40px 0;
  }
}
</style>
