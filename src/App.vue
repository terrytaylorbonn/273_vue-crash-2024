<!-- src/App.vue -->

<script setup>
import Navbar from './components/Navbar.vue';
import { RouterView} from 'vue-router';
// import Hero from '@/components/Hero.vue';
// import HomeCards from '@/components/HomeCards.vue';
// import JobListings from './components/JobListings.vue';
</script>

<template>  
  <Navbar />
  <RouterView />
  <!-- <Hero  />
  <HomeCards />
  <JobListings :limit="2" :showButton="true"/> -->
  <!-- <Hero title="Test Titleee" subtitle="Test subtitleeee" /> -->
  <!-- <h1 class="text-green-500 text-2xl">Vue jobssss</h1> -->
  </template>