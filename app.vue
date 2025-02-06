<template>
  <div>
    <NuxtRouteAnnouncer />
    <button @click="add">
      add
    </button>
    <input type="text" v-model="input" />
    <ul>
      <li v-for="item in list" :key="item">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
const input = ref<string>('')
const list = ref<string[]>([])

const add = () => {
  list.value.push(input.value)
}
</script>