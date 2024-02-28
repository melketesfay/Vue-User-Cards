<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  name: String
})
</script>
<template>
  <div v-if="name">{{ name }}</div>
</template>
<style scoped>
span {
  font-size: 1rem;
  color: rgb(15, 15, 15);
}
</style>
