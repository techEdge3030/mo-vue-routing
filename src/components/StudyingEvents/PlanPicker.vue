<script setup>
import { ref } from "vue";
import CoffeePlan from "../StudyingEvents/CoffeePlan.vue";
const plans = ref(["The Single", "The Curious", "The Addict", "The Hacker"]);

const selectedCoffeePlan = ref();
function handleSelectCoffeePlan(name) {
  selectedCoffeePlan.value = name
}
</script>

<template>
  <div class="plans">
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      :selected="plan === selectedCoffeePlan"
      @click="handleSelectCoffeePlan(plan)"
    ></CoffeePlan>
    {{ selectedCoffeePlan }}
  </div>
</template>
