<template>
  <div class="secret">
   <h1>{{ message }}</h1>
   <ul>
   <li><router-link to="/">Home</router-link></link></li>
   <li><router-link to="Survey">Survey</router-link></link></li>
   </ul>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
        message: 'check devtools!'
    }
  }
 
}
</script>

<style scoped>
.error {
  border: 1px solid #aa0000;
  padding: 1rem;
  color: #aa0000;
}
h1, h2 {
  font-weight: normal;
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
