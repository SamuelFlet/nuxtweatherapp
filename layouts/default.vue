<template>
  <div>
    <div>
      <b-navbar type="dark" variant="dark">
        <b-navbar-brand href="/">Sam's Weather App</b-navbar-brand>
        <b-navbar-nav>
          <b-nav-item href="/">Current Forecast</b-nav-item>
          <b-nav-item href="/3day">3 Day Forecast</b-nav-item>
        </b-navbar-nav>
      </b-navbar>
    </div>
    <Nuxt />
    <br /><br /><br /><br />
    <div class="jumbo">
      <b-jumbotron style="width: 50% " bg-variant="info" text-variant="white" border-variant="dark">
        <template #header>Sam's Weather App</template>

        <template #lead>
          This is a simple web app, where users can enter a location and receive the current weather or 3day forecast for it. 
        </template>

        <hr class="my-4" />

        <p>
          All data is gathered from weatherapi.com
        </p>
      </b-jumbotron>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  head() {
    return {
      meta: [
        {
          "http-equiv": "X-UA-Compatible",
          content: "IE=edge",
        },
        {
          "http-equiv": "Content-Security-Policy",
          content: "upgrade-insecure-requests",
        },
      ],
      script: [
        {
          src: "https://cdnjs.cloudflare.com/ajax/libs/vue/2.5.13/vue.js",
        },
      ],
    };
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  text-align: center;
  justify-content: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  text-align: center;
}
.jumbo{
  display:flex;
  justify-content: center;
}
</style>
