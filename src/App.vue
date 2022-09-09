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

watch(name, () => {
  if (name.value.length > 30) {
    alert("Der eingegebene Name ist zu lange.");
  }
});

watch(person, () => {
  console.log("Person was updated!");
});

watch(
  () => person.firstName,
  (newValue, oldValue) => {
    console.log(
      `First name of person was updated from "${oldValue}" to "${newValue}"`
    );
  }
);

watch(
  () => person.details,
  () => {
    console.log("Details changed!");
  },
  { deep: true }
);

const unwatchYourAgeWatcher = watchEffect(() => {
  console.log(`Your age is: ${yourAge.value}`);
});

unwatchYourAgeWatcher();
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
