<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>
<script>
import Header from './components/layout/Header'
export default {
  name: 'App',
  components: {Header}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a:hover {
  font-weight: bold;
  color: pink;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
