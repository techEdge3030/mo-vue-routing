<template>
  <div class="login">
    <form action="" class="form" @submit.prevent="login">
      <h1>Login</h1>
      <label for="username">Username</label>
      <input type="text" v-model="username" name="username" class="input" />
      <label for="password">Password</label>
      <input type="text" v-model="password" name="password" class="input" />
      <button class="btn">Login</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRoute, useRouter } from "vue-router";
const username = ref("");
const password = ref("");
const router = useRouter();
const route = useRoute();
const login = () => {
  window.user = username.value;
  const redirectPath = route.query.redirect || "/protected";
  router.push(redirectPath);
};
</script>
