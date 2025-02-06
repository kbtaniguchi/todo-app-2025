<template>
  <div>
    <NuxtRouteAnnouncer />
    <button @click="add">
      add
    </button>
    <input type="text" v-model="input" />
    <ol>
      <li v-for="item in list" :key="item.index">
        <input type="checkbox" v-model="item.isChecked" />
        {{ item.title }}
        <button @click="remove(item.index)">remove</button>
      </li>
    </ol>
  </div>
</template>

<script lang="ts" setup>
const input = ref<string>('')

type Task = {
  isChecked: boolean,
  title: string,
  index: number
}
const list = ref<Task[]>([])

const add = () => {
  list.value.push({ isChecked: false, title: input.value, index: list.value.length })
  input.value = ''
}

const remove = (index: number) => {
  list.value.splice(index, 1)
}
</script>