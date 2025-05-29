<template>
  <div id="nav">
    <AppLink to="/">
      <img src="@/assets/logo.svg" alt="logo" width="30" id="logo" />
    </AppLink>
    <AppLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </AppLink>
    <AppLink to="/login">Dashboard</AppLink>
    <AppLink to="https://vueschool.io">Vue School</AppLink>
  </div>
</template>
<script setup>
import sourceData from "@/data.json";
const destinations = sourceData.destinations;
</script>
