<template>
  <div id="nav">
    <router-link to="/">
      <img src="@/assets/logo.svg" alt="logo" width="30" id="logo" />
    </router-link>
    <router-link
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </router-link>
    <router-link to="/login">Login</router-link>
  </div>
</template>
<script setup>
import sourceData from "@/data.json";
const destinations = sourceData.destinations;
</script>
