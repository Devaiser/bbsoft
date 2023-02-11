<template>
  <RouterView v-if="isTouchScreen" />
  <Scrollbar v-else>
    <RouterView />
  </Scrollbar>
</template>

<script setup>
  import { ref, watch, onMounted } from 'vue';
  import Scrollbar from 'vue3-smooth-scrollbar';
  import { RouterView } from 'vue-router';

  const isTouchScreen = ref(null);

  const CheckTouchScreen = () => {
    isTouchScreen.value =
      'ontouchstart' in window ||
      navigator.maxTouchPoints > 0 ||
      navigator.msMaxTouchPoints > 0;
  };
  CheckTouchScreen();

  const toggleScroll = (value) => {
    if (value) {
      body.classList.remove('lock');
      app.classList.remove('smooth-scroll');
    } else {
      body.classList.add('lock');
      app.classList.add('smooth-scroll');
    }
  };

  onMounted(() => {
    const body = document.body;
    const app = document.getElementById('app');
    toggleScroll(isTouchScreen.value);
  });

  watch(isTouchScreen, (newValue) => {
    toggleScroll(newValue);
  });
</script>

<style scoped>
</style>
