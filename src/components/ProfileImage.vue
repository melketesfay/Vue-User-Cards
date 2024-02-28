<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  imgUrl: String
})
</script>
<template>
  <img :src="imgUrl" />
</template>

<style scoped>
img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
</style>
