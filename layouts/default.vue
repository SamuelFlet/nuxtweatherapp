<template>
  <div id="realapp">
    <div>
      <b-navbar style="color: white !important;">
        <b-navbar-brand href="/">Sam's Weather App</b-navbar-brand>
        <b-navbar-nav style="color: white !important;">
          <b-nav-item href="/">Current Forecast</b-nav-item>
          <b-nav-item href="/3day">3 Day Forecast</b-nav-item>
        </b-navbar-nav>
      </b-navbar>
    </div>
    <Nuxt />
    <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
    <footer>
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
    </footer>
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
#realapp{
  background-image: url('assets\725626.jpg');
  height: 100%;
  background-position: center;
  background-repeat: repeat;
  background-size: cover;
}

.navbar{
  width: 60%;
  
}

nav{
  width: 60%;
  display: flex;
  justify-content: center;
}

a{
  color: white !important;
  font-size: 1.7em;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: black;
}

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
