<template>
  <div>
    <div v-for="day in days" :key="day" class="flex items-center gap-2 mb-2">
      <input
        type="checkbox"
        v-model="checkedDays[day]"
        @change="updateProgress"
        class="checkbox checkbox-primary" />
      <span>Hari {{ day }}</span>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps({
  days: {
    type: Number,
    default: 30,
  },
});

const checkedDays = ref({});

const calculateProgress = () => {
  return Object.values(checkedDays.value).filter(Boolean).length;
};

const emit = defineEmits(["update-progress"]);
const updateProgress = () => {
  emit("update-progress", calculateProgress());
};

for (let i = 1; i <= props.days; i++) {
  checkedDays.value[i] = false;
}
</script>
