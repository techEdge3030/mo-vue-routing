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

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      window.user = this.username;
      this.$router.push({ name: "protected" });
    },
  },
};
</script>
