<template>
  <v-app>
    <v-app-bar>
      <v-header></v-header>
    </v-app-bar>
    <v-main>
      <the-dashboard />

    </v-main>
  </v-app>
</template>

<script setup>
import TheDashboard from './views/TheDashboard.vue'
import { ref, computed } from 'vue'

const userList = ref([])

fetchMockData()

async function fetchMockData() {
  const response = await fetch('http://localhost:3004/')
  const usersObject = response.json()
  const users = { usersObject }
  userList.value = users
}
</script>

<style scoped></style>
