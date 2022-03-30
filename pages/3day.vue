<template>
  <div id="app">
    <input class="shadow-xl" v-model="name" />
    <button class="shadow-xl" @click="fetchAxios">Get input field value</button>
    <div>
      <h1 v-if="results.location">{{results.location.name}}</h1>
      <div class="d-flex" v-if="results.location" id="card2">
        <div style="padding: 10px" v-for="i in results.forecast.forecastday" :key="i.id">
          <b-card
            v-if="results.location"
            id="card"
            style="width: 25rem;"
          >
            <b-card-text v-if="i.day">
              <h3>{{ i.date }}</h3>
              <div class="d-flex justify-content-center">
                <p id="temp">{{ i.day.avgtemp_c }}°C</p>
                <p style="margin-top: 3.15rem">
                  &emsp;Max: {{ i.day.maxtemp_c }}°C
                  <br>
                  &emsp;Min: {{ i.day.mintemp_c }}°C
                </p>
              </div>
              <img
                v-if="i.day.condition"
                :src="i.day.condition.icon"
              />
            </b-card-text>
            <b-card-text v-if="i.day">
              <div class="d-flex justify-content-md-center">
                <p v-if="i.day">
                  Wind: {{ i.day.maxwind_kph }} kph&emsp;
                </p>
                <p v-if="i.day">
                  Rain Chance: {{ i.day.daily_chance_of_rain }} %
                </p>
              </div>
            </b-card-text>
            <b-card-text v-if="i.day">
              <div class="d-flex justify-content-md-center">
                <p v-if="i.day">
                  Humidity: {{ i.day.avghumidity }}%&emsp;
                </p>
              </div>
            </b-card-text>
          </b-card>
        </div>
      </div>
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
h1{
  padding-top: 10px;
}
#card2{
  justify-content: center;
  margin-right:10%
}
#temp {
  padding-top: 5%;
  font-size: 4rem;
}



</style>
