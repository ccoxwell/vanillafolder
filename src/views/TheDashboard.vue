<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-card title="User Info">
          <v-card-text>
            <p>Name: {{ currentUser.firstName }} {{ currentUser.lastName }}</p>
            <p>Address: {{ currentUser.address }}</p>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12">
        <v-card title="Emergency Info">
          <v-card-text>
            <p>Allergies: {{ currentUser.allergies }}</p>
            <p>Medications: {{ currentUser.medicationList }}</p>
            <v-card-text>
            <p>Emergency Contact: </p>
            <p>{{ currentUser.emergencyContact.firstName }} {{ currentUser.emergencyContact.lastName }}</p>
            <p>{{ currentUser.emergencyContact.phone }}</p>
            <p>{{ currentUser.emergencyContact.email }}</p>
            <p>{{ currentUser.emergencyContact.address }}</p>
            </v-card-text>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12">
        <v-card title="Vault">
          <v-card-text> This will be a grid of PDFs at some point </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12">
        <v-card title="Calendar">
          <v-date-picker v-model="date" />
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, computed } from 'vue'
import "v-calendar/dist/style.css";

const USER_ID = "63fb7794a745b07e9fa6a45b"

const users = ref([])

const currentUser = computed(() => users.value.find(user => user._id == USER_ID))

getUserList()

function getUserList() {
  fetchUsers().then(response => {
    users.value = response
  })
}

async function fetchUsers() {
  const response = await fetch("http://localhost:3004/users")
  const body = response.json();
  return body;
}

</script>
