<template>
  <section class="section">
    <div>
      <h2 class="title">
        <span class="gray-gradient">stay in the </span>
        <span class="yellow-gradient">bb</span>
      </h2>
      <form class="form" @submit.prevent="onSubmit">
        <Transition mode="out-in">
          <div class="input-wrapper" v-if="!isSuccessVisible">
            <input
              type="email"
              name="email"
              placeholder="your email"
              class="input"
              v-model="email"
            />
            <button type="submit" class="submit-button">Subscribe</button>
          </div>
          <div class="form__success" v-else>Subscribed</div>
        </Transition>
      </form>
      <div class="gradient-top"></div>
      <div class="bg">
        <video preload="metadata" autoplay muted loop playsinline class="video">
          <source type="video/mp4" src="/video/bg.mp4" v-if="width > 556" />
          <source type="video/mp4" src="/video/media-bg.mp4" v-else />
          <img src="/img/bg.jpg" alt="bg" class="image" />
        </video>
      </div>
    </div>
    <Footer />
    <div class="gradient-bottom"></div>
  </section>
</template>
<script setup>
import { ref } from 'vue';
import { Footer } from '@/components';
import { useWindowSize } from '@vueuse/core';

const email = ref('');
const isSuccessVisible = ref(false);

const { width } = useWindowSize();

const onSubmit = (e) => {
  const formData = new FormData(e.target);
  fetch('https://getform.io/f/5c28fdc4-ee75-43dc-9cee-e5d461d3c8e2', {
    method: 'POST',
    body: formData,
    headers: {
      Accept: 'application/json',
    },
  })
    .then(() => {
      isSuccessVisible.value = true;
      setTimeout(() => {
        isSuccessVisible.value = false;
      }, 3000);
      email.value = '';
    })
    .catch((error) => console.log(error));
};
</script>
<style scoped>
.section {
  position: relative;
  padding-top: 30vh;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.title {
  font-weight: 900;
  font-size: 110px;
  line-height: 1.06;
  position: relative;
  z-index: 1;
  width: fit-content;
  margin: 0 auto;
  text-align: center;
}
.form {
  margin-top: 80px;
  display: flex;
  justify-content: center;
}
.input-wrapper {
  position: relative;
  background: rgba(0, 0, 0, 0.24);
  border: 3px solid rgba(255, 167, 26, 0.5);
  border-radius: 11px;
  overflow: hidden;
  width: 463px;
  height: 70px;
}
.input {
  width: calc(100% - 125px);
  height: 100%;
  padding: 10px 0px 10px 37px;
  box-sizing: border-box;
  border: none;
  background: linear-gradient(98.27deg, #ffa71a 17.57%, #000000 85.54%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
  font-weight: 900;
  font-size: 18px;
  line-height: 1.06%;
  outline: none;
}
.input::placeholder {
  text-transform: uppercase;
  background: linear-gradient(98.27deg, #ffa71a 17.57%, #000000 45.54%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
  font-weight: 900;
  font-size: 15px;
  line-height: 1.06%;
}
.submit-button {
  position: absolute;
  top: 50%;
  right: 0px;
  padding-right: 10px;
  height: 100%;
  background: none;
  border: none;
  cursor: pointer;
  transform: translateY(-50%);
  background: linear-gradient(98.27deg, #474343 0%, #888686 105.42%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
  font-weight: 900;
  font-size: 20px;
  line-height: 1.06%;
}
.form__success {
  width: 463px;
  height: 70px;
  border-radius: 94px;
  display: flex;
  justify-content: center;
  align-items: center;
  -webkit-box-shadow: 12px 13px 17px -3px rgba(0, 0, 0, 0.37);
  -moz-box-shadow: 12px 13px 17px -3px rgba(0, 0, 0, 0.37);
  box-shadow: 12px 13px 17px -3px rgba(0, 0, 0, 0.37);
  background: linear-gradient(98.27deg, #ffa71a 0%, #000000 180.42%);
  font-weight: 700;
  font-size: 26px;
  line-height: 1.25;
  text-transform: uppercase;
  color: #fff;
}
.gradient-bottom {
  display: none;
}
@media (max-width: 992px) {
  .section {
    padding: 0 40px;
    padding-top: 30vh;
  }
  .title {
    font-size: 80px;
  }
}
@media (max-width: 768px) {
  .title {
    font-size: 62px;
  }
  .gradient-top {
    height: 200px;
  }
  .gradient-bottom {
    display: block;
  }
}
@media (max-width: 556px) {
  .title {
    font-size: +50px;
  }
  .section {
    padding: 0 20px;
    padding-top: 30vh;
  }
  .input {
    padding: 10px 0px 10px 20px;
  }
}
</style>
