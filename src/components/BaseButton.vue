<template>
  <a :href="link" target="_blank" class="button" :class="{ disabled: !link }">
    <span>{{ value }}</span>
  </a>
</template>
<script setup>
defineProps({
  value: {
    type: String,
    required: true,
  },
  link: {
    type: String,
    required: false,
  },
});
</script>
<style scoped>
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(180deg, #ffa71a 0%, #1d1d1d 100%);
  border-radius: 11px;
  width: 169px;
  height: 46px;
}
.button span {
  background: linear-gradient(98.27deg, #000000 0%, #000000 105.42%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
  font-weight: 900;
  font-size: 15px;
  line-height: 1.06;
  text-transform: uppercase;
}
.disabled {
  pointer-events: none;
}
@media (max-width: 992px) {
  .button {
    width: 200px;
    height: 60px;
  }
  .button span {
    font-size: 20px;
  }
}
@media (max-width: 556px) {
  .button {
    width: 80%;
    height: 70px;
  }
  .button span {
    font-size: 20px;
  }
}
</style>
