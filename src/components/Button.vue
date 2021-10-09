<template>
  <button class="primary-button" :class="{reverse: reverse, 'button-shadow': shadow}">
    <slot />
  </button>
</template>

<script setup>
defineProps({
  reverse: {
    type: Boolean,
    default: false,
  },
  shadow: {
    type: Boolean,
    default: true
  },
})
</script>