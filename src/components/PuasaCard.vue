<template>
  <div class="card bg-base-100 shadow-xl">
    <div class="card-body">
      <h2 class="card-title">
        Hari {{ days[0] }} - {{ days[days.length - 1] }}
      </h2>
      <div>
        <div
          v-for="day in days"
          :key="day"
          class="flex items-center gap-2 mb-2">
          <input
            type="checkbox"
            v-model="checkedDays[day]"
            @change="updateProgress"
            class="checkbox checkbox-primary" />
          <span>Hari {{ day }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps({
  days: {
    type: Array,
    required: true,
  },
  checkedDays: {
    type: Object,
    required: true,
  },
});

const emit = defineEmits(["update-progress"]);
const updateProgress = () => {
  const progress = Object.values(props.checkedDays).filter(Boolean).length;
  emit("update-progress", progress);
};
</script>
