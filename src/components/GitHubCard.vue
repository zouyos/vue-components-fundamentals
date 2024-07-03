<script setup>
import { ref } from 'vue'
const props = defineProps({
  username: { type: String, required: true }
})

const user = ref()

fetch(`https://api.github.com/users/${props.username}`).then(async (res) => {
  const data = await res.json()
  user.value = data
})
</script>

<template>
  <div v-if="user" class="card" style="width: 18rem">
    <img :src="user.avatar_url" class="card-img-top" :alt="user.login" />
    <div class="card-body">
      <h5 class="card-title">{{ user.login }}</h5>
      <p class="card-text">
        Some quick example text to build on the card title and make up the bulk of the card's
        content.
      </p>
      <a :href="user.html_url" class="btn btn-primary">View profile</a>
    </div>
  </div>
</template>
