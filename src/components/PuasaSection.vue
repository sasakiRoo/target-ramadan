<template>
  <div class="puasa-section h-96 overflow-y-auto">
    <SectionHeader
      title="Puasa Ramadan"
      :progress="progressPuasa"
      :total="30" />
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <PuasaCard
        v-for="(chunk, index) in chunkedDays"
        :key="index"
        :days="chunk"
        :checkedDays="checkedDays"
        @update-progress="updateProgressPuasa" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";
import SectionHeader from "./SectionHeader.vue";
import PuasaCard from "./PuasaCard.vue";

const progressPuasa = ref(0);

const checkedDays = ref({});

const chunkedDays = computed(() => {
  const days = Array.from({ length: 30 }, (_, i) => i + 1);
  const chunkSize = 5;
  return Array.from({ length: Math.ceil(days.length / chunkSize) }, (_, i) =>
    days.slice(i * chunkSize, i * chunkSize + chunkSize)
  );
});

const updateProgressPuasa = (newProgress) => {
  progressPuasa.value = newProgress;
  saveToLocalStorage();
};

const saveToLocalStorage = () => {
  localStorage.setItem(
    "puasaProgress",
    JSON.stringify({
      progress: progressPuasa.value,
      checkedDays: checkedDays.value,
    })
  );
};

onMounted(() => {
  const savedData = localStorage.getItem("puasaProgress");
  if (savedData) {
    const { progress, checkedDays: savedCheckedDays } = JSON.parse(savedData);
    progressPuasa.value = progress;
    checkedDays.value = savedCheckedDays;
  }
});
</script>

<style scoped>
.puasa-section {
  margin-bottom: 2rem;
}
</style>
