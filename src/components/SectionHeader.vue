<template>
  <div class="flex justify-between items-center mb-4">
    <h1 class="text-2xl font-bold">{{ title }}</h1>
    <ProgressIndicator :progress="progress" :total="total" />
  </div>
</template>

<script setup>
import ProgressIndicator from "./ProgressIndicator.vue";

defineProps({
  title: String,
  progress: Number,
  total: Number,
});
</script>
