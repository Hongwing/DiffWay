<template>
  <div id="app">
    <img alt="Vue logo" width="120" height="120" src="./assets/logo.png">
    <div class="dw-main">
      <home></home>
    </div>
  </div>
</template>

<script>
import Home from './pages/Home'

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
