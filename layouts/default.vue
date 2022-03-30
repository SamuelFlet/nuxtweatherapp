<template>
  <div>
    <div>
      <b-navbar type="dark" variant="dark">
        <b-navbar-nav>
          <b-nav-item><NuxtLink to="/">Current Forecast</NuxtLink></b-nav-item>
          <b-nav-item text="Lang"><NuxtLink to="/3day">3 Day Forecast</NuxtLink></b-nav-item>
        </b-navbar-nav>
      </b-navbar>
    </div>
    <Nuxt />
    <br><br><br><br>
    <h1>I will explain this later</h1>
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
h1{
  text-align: center;
}
</style>
