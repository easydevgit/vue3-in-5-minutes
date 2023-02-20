<script setup>
import TestComponent from '../components/TestComponent.vue'
import { onMounted, reactive, ref } from 'vue'

const count = reactive({ number: 1 })
const showText = ref(true)

function increment() {
  count.number++
}

onMounted(() => {
  console.log(`The initial count is ${count.number}.`)
})

function catchUpdate() {
  showText.value = !showText.value
}

</script>

<template>
  <main>
    <TestComponent :count="count.number" @update="catchUpdate" ></TestComponent>
    <div v-show="showText">Hello Vue</div>
    <button @click="increment"> Add 1 to count </button>
  </main>
</template>
