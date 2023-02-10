<template>
  <a :href="link" class="button" :class="{ disabled: !link }">
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
    },
  });
</script>
<style scoped>
  .button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 157px;
    height: 30px;
    background: #000;
    border-radius: 10px;
    border: 1px solid #156d66;
    border-bottom: none;
  }
  .button span {
    font-weight: 700;
    font-size: 16px;
    line-height: 1.25;
    color: #21e7d6;
  }
  .disabled {
    pointer-events: none;
  }
</style>