<template>
  <a :href="link" class="button">
    <span>
      {{ value }}
    </span>
  </a>
</template>
<script setup>
  const props = defineProps({
    value: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: false,
      default: '#',
    },
  });
</script>
<style scoped>
  .button {
    background: linear-gradient(180deg, #83daff 0%, #21e7d6 100%);
    border-radius: 10px;
    width: 110px;
    height: 35px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .button span {
    font-weight: 700;
    font-size: 16px;
    line-height: 1.25;
    color: #000;
  }

  @media (max-width: 400px) {
    .button {
      width: 90px;
    }
  }
</style>