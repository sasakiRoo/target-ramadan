<template>
  <div class="sholat-section h-96 overflow-y-auto">
    <SectionHeader title="Sholat" :progress="progressSholat" :total="150" />
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <HariCollapse
        v-for="day in 30"
        :key="day"
        :day="day"
        :checkedSholat="checkedSholat[day] || {}"
        @update-progress="updateProgressSholat" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";
import SectionHeader from "./SectionHeader.vue";
import HariCollapse from "./HariCollapse.vue";

const progressSholat = ref(0);

const checkedSholat = ref({});

const updateProgressSholat = (newProgress) => {
  progressSholat.value = newProgress;
  saveToLocalStorage();
};

const saveToLocalStorage = () => {
  localStorage.setItem(
    "sholatProgress",
    JSON.stringify({
      progress: progressSholat.value,
      checkedSholat: checkedSholat.value,
    })
  );
};

onMounted(() => {
  const savedData = localStorage.getItem("sholatProgress");
  if (savedData) {
    const { progress, checkedSholat: savedCheckedSholat } =
      JSON.parse(savedData);
    progressSholat.value = progress;
    checkedSholat.value = savedCheckedSholat;
  }
});
</script>

<style scoped>
.sholat-section {
  margin-bottom: 2rem;
}
</style>
