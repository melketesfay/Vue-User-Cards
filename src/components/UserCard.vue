<script setup>
import { onBeforeMount, onMounted, ref } from 'vue'
import FetchButton from '@/components/FetchButton.vue'
import ProfileInfo from '@/components/ProfileInfo.vue'
import ProfileImage from '@/components/ProfileImage.vue'

const imgUrl = ref('')
const firstName = ref('')
const lastName = ref('')
const userEmail = ref('')

async function fetchData() {
  const res = await fetch('https://randomuser.me/api/')
  const data = await res.json()
  firstName.value = data.results[0].name.first
  lastName.value = data.results[0].name.last
  userEmail.value = data.results[0].email
  imgUrl.value = data.results[0].picture.medium
}

fetchData()
</script>

<template>
  <div class="user-container">
    <ProfileImage :imgUrl="imgUrl" />
    <div class="user-name-container">
      <ProfileInfo :name="firstName" /> <ProfileInfo :name="lastName" />
    </div>
    <ProfileInfo class="user-email" :name="userEmail" />
    <FetchButton class="card-button" @click="fetchData()" />
  </div>
</template>
<style>
.user-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;

  width: 200px;
  height: fit-content;
  padding: 2rem;

  background-color: rgb(255, 255, 255);
  border-radius: 0.25rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.user-container:hover {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}
.user-name-container {
  display: flex;
  gap: 0.25rem;
  flex-direction: row;
}
.user-email {
  font-size: 0.75rem;
  color: rgb(15, 15, 15);
}
.card-button {
  width: 100%;
  border-radius: 1rem;
  font-size: 1.5rem;
}
</style>
