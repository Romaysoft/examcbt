<template>
  <Navbar />
  <Hero />
  <AboutUs />
  <WhyChooseUs />
  <Stats />
  <WaysToUse />
  <Footer />
  <!-- Rest of your app content -->
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import AboutUs from './components/AboutUs.vue'
import Stats from './components/Stats.vue'
import WhyChooseUs from './components/WhyChooseUs.vue'
import WaysToUse from './components/WaysToUse.vue'
import Footer from './components/Footer.vue'
</script>

<style>
/* Make sure you have this if you're using Tailwind */
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
