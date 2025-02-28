<script setup>
import PuasaSection from "./components/PuasaSection.vue";
import SholatSection from "./components/SholatSection.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <h1 class="font-bold my-10 text-4xl text-center">
    Selamat berpuasa {{ new Date().getFullYear() }}
  </h1>
  <div class="container mx-auto p-4">
    <PuasaSection />
    <SholatSection />
  </div>
  <Footer />
</template>
