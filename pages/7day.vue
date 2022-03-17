<template>
  <div id="app">
    <input class="shadow-xl" v-model="name" />
    <button class="shadow-xl" @click="fetchAxios">Get input field value</button>
    <div>
      <b-card v-if="results.location" :title="results.location.name" id="card">
       <b-card-text>
            <p v-for="i in results.forecast.forecastday">
              {{ i.date }}
              {{ i.day.maxtemp_c }}
            </p>
       </b-card-text>
      </b-card>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "IndexPage",
  data() {
    return {
      results: [],
      name: "",
    };
  },
  methods: {
    fetchAxios() {
      axios
        .post(
          "http://api.weatherapi.com/v1/forecast.json?Key=6cc51e6401484112b72142155221701&days=7&q=" +
            this.name
        )
        .then((response) => {
          this.results = response.data;
        });
    },
  },
};
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

#temp {
  font-size: 4rem;
}

#card {
  margin-top: 50px;
  margin-left: 30%;
  margin-right: 30%;
}

img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
