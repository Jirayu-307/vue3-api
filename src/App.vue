<script setup>
import axios from "axios";
import { ref } from "vue";

const data = ref();
const config = {
  method: "get",
  url: "https://v2.jokeapi.dev/joke/Any?safe-mode",
  headers: {
    "Access-Control-Allow-Origin": "*",
  },
};

axios(config)
  .then(function (response) {
    data.value = response.data;
  })
  .catch(function (error) {
    console.log(error);
  });
</script>
<template>
  <h1>JokeApi</h1>


  <br>
  <h1>{{ data["setup"] }}</h1>
  <h4>{{ data.delivery }}</h4>
</template>

<style scoped></style>
