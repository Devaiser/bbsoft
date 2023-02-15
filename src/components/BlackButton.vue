<template>
  <a :href="link" class="button" @click="toggleValue">
    <Transition mode="out-in">
      <span v-if="isValueVisible">
        {{ value }}
      </span>
      <span v-else>
        {{ descr }}
      </span>
    </Transition>
  </a>
</template>
<script setup>
import { ref } from 'vue';
defineProps({
  value: {
    type: String,
    required: true,
  },
  descr: {
    type: String,
    required: false,
  },
  link: {
    type: String,
    required: false,
  },
});
const isValueVisible = ref(true);
const toggleValue = () => {
  isValueVisible.value = !isValueVisible.value;
};
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
</style>
