<template>
  <div id="app">
    <div>
      <input v-model="name" />
      <button class="shadow-xl" @click="fetchAxios">Get input field value</button>
      <br />
      <div v-for="result in results" :key="result.current">
        {{ result.temp_c }}
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'IndexPage',
  data() {
    return {
      results: [],
      name: "",
    };
  },
  methods: {
    fetchAxios() {
      axios.get("http://api.weatherapi.com/v1/current.json?Key=6cc51e6401484112b72142155221701&q=" + this.name)
        .then((response) => {this.results = response.data;});
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
