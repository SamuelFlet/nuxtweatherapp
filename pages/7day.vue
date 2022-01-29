<template>
  <div id="app">
    <input class="shadow-xl" v-model="name" />
    <button class="shadow-xl" @click="fetchAxios">Get input field value</button>
    <div>
      <b-card v-if="results.location" :title="results.location.name" id="card">
        <b-card-text v-if="results.current">
          <div class="d-flex justify-content-center">
            <p id="temp">{{ results.current.temp_c }}°C</p>
            <p style="margin-top: 3.15rem">
              &emsp;Feels Like: {{ results.current.feelslike_c }}°C
            </p>
          </div>
          <img v-if="results.current" :src="results.current.condition.icon" />
        </b-card-text>
        <b-card-text v-if="results.current">
          <div class="d-flex justify-content-md-center">
            <p v-if="results.current">
              Wind: {{ results.current.wind_kph }} kph&emsp;
            </p>
            <p v-if="results.current">
              Wind Direction: {{ results.current.wind_dir }}
            </p>
          </div>
        </b-card-text>
        <b-card-text v-if="results.current">
          <div class="d-flex justify-content-md-center">
            <p v-if="results.current">
              Humidity: {{ results.current.humidity }}%&emsp;
            </p>
            <p v-if="results.current">Cloud: {{ results.current.cloud }}%</p>
          </div>
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
          "http://api.weatherapi.com/v1/current.json?Key=6cc51e6401484112b72142155221701&q=" +
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
