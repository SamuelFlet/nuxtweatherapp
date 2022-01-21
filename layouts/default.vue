<template>

  <main id="app">

    <img style="margin-left: auto; margin-right: auto;" src="~assets/New_Logo-preview.png"/>
    <Nuxt/>
  </main>
</template>

<script>
export default {
  name: "App",
  head(){
    return{
      meta:[
        {
          "http-equiv":"X-UA-Compatible",
          content:"IE=edge"
        },
        {
          "http-equiv":"Content-Security-Policy",
          content:"upgrade-insecure-requests"
        },
      ]
    }
  }
}
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
</style>
