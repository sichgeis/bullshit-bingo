<template>
  <div class="card">
    {{ title }}
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string
}>()
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
