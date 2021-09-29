<template>
  <div id="app">
    <ListaDiEmail msg="Randomic emails:" :listaEmails="listaEmails"/>
  </div>
</template>

<script>
import ListaDiEmail from './components/Email.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    ListaDiEmail
  },

  data(){
    return {
      listaEmails: [],
    }
  },

  mounted(){
    console.log(axios)

    for(let i = 0; i < 10; i++){
      axios.get("https://flynn.boolean.careers/exercises/api/random/mail")
      .then((response) => { 
      this.listaEmails.push(response.data.response);
      console.log(this.listaEmails)
      })
    }
      
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
