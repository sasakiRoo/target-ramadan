<template>
  <div class="text-sm text-gray-600">{{ progress }}/{{ total }}</div>
</template>

<script setup>
defineProps({
  progress: Number,
  total: Number,
});
</script>
