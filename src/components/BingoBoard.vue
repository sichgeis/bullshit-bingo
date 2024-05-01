<template>
  <div class="container">
    <BingoCard v-for="i in 25" :key="i" :title="titleList[i - 1]" />
  </div>
</template>

<script setup lang="ts">
import BingoCard from './BingoCard.vue'

const titleList = [
  'Domain Specific Learning',
  'Prompt',
  'Training',
  'Context-Injection',
  'Pre-Training',
  'Fine-Tuning',
  'Zero-Shot Learning',
  'Few-Shot Learning',
  'One-Shot Learning',
  'RAG (Retrieval-Augmented Generation)',
  'Open Source Model',
  'Proprietary Model',
  'Function Calling',
  'Vector Datenbank',
  'Long-Term Memory',
  'Agents',
  'Hallucinations',
  'Inference Speed',
  'Time To First Token',
  'Coding Agents',
  'Knowledge Distillation',
  'Reinforcement Learning',
  'Transformer',
  'Unsupervised Learning',
  'Word Embedding',
]
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 10px;
}
</style>
