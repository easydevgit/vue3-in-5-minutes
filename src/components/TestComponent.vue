<script setup>
const props = defineProps({
  // props go here
  count: Number
})

const emit = defineEmits(['update'])

function buttonClick() {
  emit('update')
}

</script>

<template>
  <div class="test-component">
    <h1>Test Component {{count}}</h1>
    <button @click="buttonClick"> Event from Child Component </button>
  </div>
</template>

<style scoped>
.test-component {
  text-align: center;
  font-size: 36px;
  color: blueviolet;
}
</style>
