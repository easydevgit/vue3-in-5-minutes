<script setup>
import TestComponent from '../components/TestComponent.vue'
import { onMounted, reactive, ref } from 'vue'

const count = reactive({ number: 1 })

function increment() {
  count.number++
}

onMounted(() => {
  console.log(`The initial count is ${count.number}.`)
})

function catchUpdate() {
  console.log(`Event from child component received.`)
}

</script>

<template>
  <main>
    <TestComponent :count="count.number" @update="catchUpdate" ></TestComponent>
    Hello Vue
    <button @click="increment"> Add 1 to count </button>
  </main>
</template>
