<template>
  <UApp>
    <NuxtRouteAnnouncer />
    <UContainer>
      <h1 class="text-2xl">TODO APP</h1>
    <UButton @click="add">
      add
    </UButton>
    <UInput type="text" v-model="input" />
    <ol>
      <li v-for="(item, index) in list" :key="index">
        <UCheckbox type="checkbox" v-model="item.isChecked" />
        {{ item.title }}
        <UButton @click="remove(index)">remove</UButton>
      </li>
    </ol>
    </UContainer>
  </UApp>
</template>

<script lang="ts" setup>
const input = ref<string>('')

type Task = {
  isChecked: boolean,
  title: string
}
const list = ref<Task[]>([])

const add = () => {
  list.value.push({ isChecked: false, title: input.value })
  input.value = ''
}

const remove = (index: number) => {
  list.value.splice(index, 1)
}
</script>