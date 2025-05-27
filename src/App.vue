<template>
  <TheNavigation />
    <div class="container">
     <router-view :key="$route.path"></router-view>
   </div>
</template>

<script setup>
import TheNavigation from './components/TheNavigation.vue';
</script>