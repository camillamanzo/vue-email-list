<template>
  <div id="app">
    <Email msg="Randomic emails:"
    :email="emailRandomica" />
  </div>
</template>

<script>
import Email from './components/Email.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Email
  },

  data(){
    return {
      emailRandomica : ""
    }
  },

  mounted(){
    console.log(axios)

    axios.get("https://flynn.boolean.careers/exercises/api/random/mail")
    .then((response) => { this.emailRandomica = response.data.response;})
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
