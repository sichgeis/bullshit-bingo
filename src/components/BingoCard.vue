<template>
  <div class="card" @click="toggleFlipped">
    <div v-if="isFlipped">{{ text }}</div>
    <div v-else>{{ title }}</div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

defineProps<{
  title: string;
  text: string;
}>()

const isFlipped = ref(false)

const toggleFlipped = () => {
  isFlipped.value = !isFlipped.value
}
</script>

<style scoped>
.card {
  background-color: aquamarine;
  justify-content: center;
  align-items: center;
  display: flex;
  width: 100%;
  aspect-ratio: 1;
  text-align: center;
  padding: 1rem;
}
</style>
