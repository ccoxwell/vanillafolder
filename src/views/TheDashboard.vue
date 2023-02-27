<script setup>
import 'v-calendar/dist/style.css';


</script>

<template>
    <v-container>
        <v-row>
            <v-col cols="12">
        <v-card 
        title="User Info"
        >
            <v-card-text>
               <p>Name: </p>
               <p>Address: </p>
            </v-card-text>
        </v-card>
    </v-col>
    <v-col cols="12">
        <v-card
        title="Emergency Info">
            <v-card-text>
                <p>Allergies:</p>
                <p>Medical Issues:</p>
                <p>Emergency Contact:</p>
                <p>Medications:</p>
            </v-card-text>
        </v-card>
    </v-col>
    <v-col cols="12">
        <v-card
        title="Vault">
            <v-card-text>
                This will be a grid of PDFs at some point
            </v-card-text>
        </v-card>
    </v-col>
    <v-col cols="12">
        <v-card
        title="Calendar">
            <v-date-picker v-model="date" />
        </v-card>
    </v-col>
        </v-row>
    </v-container>
</template>