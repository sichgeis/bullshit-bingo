<template>
  <div class="container" @click.stop>
    {{ title }}: {{ text }}
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string;
  text: string;
}>()
</script>

<style scoped>
.container {
  background-color: aquamarine;
  justify-content: center;
  align-items: center;
  display: flex;
  width: 50%;
  max-width: 30rem;
  aspect-ratio: 1;
  text-align: center;
  padding: 1rem;
}
</style>
