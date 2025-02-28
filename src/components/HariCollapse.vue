<template>
  <div class="hari-collapse mb-4">
    <div
      class="flex justify-between items-center bg-gray-800 p-3 rounded-lg cursor-pointer"
      @click="toggleCollapse">
      <h3 class="font-semibold">Hari {{ day }}</h3>
      <span>{{ isCollapsed ? "▼" : "▲" }}</span>
    </div>
    <div v-if="!isCollapsed" class="mt-2 pl-4">
      <div
        v-for="waktu in waktuSholat"
        :key="waktu"
        class="flex items-center gap-2 mb-2">
        <input
          type="checkbox"
          v-model="checkedSholat[waktu]"
          @change="updateProgress"
          class="checkbox checkbox-primary" />
        <span>{{ waktu }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps({
  day: {
    type: Number,
    required: true,
  },
  checkedSholat: {
    type: Object,
    required: true,
  },
});

const isCollapsed = ref(false);

const waktuSholat = ["Subuh", "Dhuhur", "Ashar", "Maghrib", "Isha"];

const checkedSholat = ref({ ...props.checkedSholat });

const calculateProgress = () => {
  return Object.values(checkedSholat.value).filter(Boolean).length;
};

const emit = defineEmits(["update-progress"]);
const updateProgress = () => {
  emit("update-progress", calculateProgress());
};

const toggleCollapse = () => {
  isCollapsed.value = !isCollapsed.value;
};

watch(
  checkedSholat,
  () => {
    emit("update-progress", calculateProgress());
  },
  { deep: true }
);
</script>

<style scoped>
.hari-collapse {
  border: 1px solid #e2e8f0;
  border-radius: 0.5rem;
  padding: 0.5rem;
}
</style>
