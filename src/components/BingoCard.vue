<template>
  <div class="card" @click="toggleFlipped">
    {{ title }}
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps<{
  title: string;
  index: number;
}>()
const emit = defineEmits(['flipped']);

const isFlipped = ref(false)

const toggleFlipped = () => {
  isFlipped.value = !isFlipped.value

  emit('flipped', props.index)
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

  @media only screen and (max-width: 600px) {
    font-size: xx-small;
  }

  /* padding: 1rem; */
}
</style>
