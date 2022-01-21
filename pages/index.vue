<template>
  <div id="app">
    <input class="shadow-xl" v-model="name" />
    <button class="shadow-xl" @click="fetchAxios">Get input field value</button>

    <div class="box-border flex justify-center shadow-xl" id="card">
      <div id="test">
          <div v-for="result in results" :key="result.current">
            <p class="text-7xl">{{result.temp_c}}</p>
          </div>
          <div v-for="cons in results.current" :key="cons.condition">
            <img class="object-center" :src="cons.icon">
          </div>
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
  justify-content: center;
  color: #2c3e50;
  margin-top: 60px;
}

#card{
  margin-top:50px;
  margin-left: 30%;
  margin-right: 30%;
}
</style>
