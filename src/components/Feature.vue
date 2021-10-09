<template>
    <div class="head">
      <div class="label">0{{num}}</div>
      <h3>{{ title }}</h3>
    </div>

    <div class="about">
      <h3>{{ title }}</h3>
      <p><slot /></p>
    </div>
</template>

<script setup>

defineProps({
  num: Number,
  title: String
});

</script>