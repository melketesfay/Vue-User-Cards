<script setup>
import UserCard from '@/components/UserCard.vue'
</script>
<template>
  <main>
    <UserCard />
    <UserCard />
    <UserCard />
    <UserCard />
  </main>
</template>

<style scoped>
main {
  display: flex;
  gap: 1rem;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
