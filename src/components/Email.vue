<template>
  <div class="Emails">
    <h1>{{ msg }}</h1>
    <ul>
      <li  v-for="(element, index) in listaEmails" :key="index"> {{ element }}</li>
    </ul>
    
  </div>
</template>

<script>

export default {
  name: 'ListaDiEmail',
  props: {
    msg: String,
    listaEmails: Array,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
