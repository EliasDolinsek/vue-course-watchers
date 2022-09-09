<script setup>
import { watchEffect } from "vue";
import { reactive } from "vue";
import { ref, watch } from "vue";

const name = ref("Max Mustermann");
const yourAge = ref(25);

const person = reactive({
  firstName: "Elon",
  lastName: "Musk",
  details: {
    netWorth: 259,
    age: 51,
  },
});

// TODO: 1. Erstelle einen Watcher, welcher einen Alert ausgibt, sobald die Länge von "name" > 30 ist

// TODO: 2. Gib auf der Konsole aus, wenn sich "person" verändert hat

// TODO: 3. Gib auf der Konsole aus, sobald sich "firstName" von "person" verändert hat. Inklusive oldValue und newValue.

// TODO: 4. Erstelle einen Deep-Watcher für "details" von "person", welcher ausgibt sobald sich dieses Objekt verändert hat

// TODO: 5. Erstelle einen watchEffect-Watcher, welcher "yourAge" ausgibt, sobald es sich verändert hat

// TODO: 6. Stoppe den "yourAge"-Watcher manuell
</script>

<template>
  <main>
    <p>Name:</p>
    <input v-model="name" type="text" />
    <hr />

    <p>First Name:</p>
    <input v-model="person.firstName" type="text" />
    <p>Last Name:</p>
    <input v-model="person.lastName" type="text" />
    <p>Net Worth (Billion):</p>
    <input v-model="person.details.netWorth" type="number" />
    <p>Age:</p>
    <input v-model="person.details.age" type="number" />
    <hr />

    <p>Enter your age:</p>
    <input v-model="yourAge" />
  </main>
</template>

<style scoped></style>
