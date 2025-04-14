<template>
  <div :class="['flex flex-col', `gap-6`]">
    <slot/>
  </div>
</template>

<script setup lang="ts">
defineProps({
  gap: {
    type: String,
    default: '6'
  }
})
</script>