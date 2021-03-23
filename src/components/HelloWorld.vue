<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
       {{ info }}
    </p>
  </div>  
</template>

<script>
const axios = require('axios').default

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('http://127.0.0.1:8000/api/sezioni/?format=json')
      .then(response => (this.info = response))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
