<script setup>
import { ref } from "vue";
const props = defineProps({
  username: { type: String, required: true },
});
const user = ref();
fetch(`https://api.github.com/users/${props.username}`).then(async (res) => {
  const data = await res.json();
  user.value = data;
});
</script>
<template>
  <div v-if="user">
    <!-- <pre>{{ user }}</pre> -->
    <div class="card card-side bg-base-100 shadow-sm">
      <figure>
        <img :src="user.avatar_url" class="w-48 rounded-full" />
      </figure>
      <div class="card-body">
        <h2 class="card-title">{{ user.login }}</h2>
        <p>Followers: {{ user.followers }}</p>
        <p>Following: {{ user.following }}</p>
        <div class="card-actions justify-end">
          <a class="btn btn-primary" :href="user.html_url">View Profile</a>
        </div>
      </div>
    </div>
  </div>
</template>
