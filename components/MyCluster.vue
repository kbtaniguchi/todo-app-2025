<template>
  <div :class="['flex flex-wrap items-center', `gap-${gap}`]">
    <slot/>
  </div>
</template>

<script setup lang="ts">
defineProps({
  gap: {
    type: String,
    default: '4'
  }
})
</script>