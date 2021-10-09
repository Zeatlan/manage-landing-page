<template>
  <img :src="require(`@/assets/img/${avatar}.png`)" :alt="name + ' avatar'" />

  <div class="body">
    <h3>{{ name }}</h3>
    <p>"<slot />"</p>
  </div>
</template>

<script setup>

defineProps({
  avatar: String,
  name: String
});
</script>