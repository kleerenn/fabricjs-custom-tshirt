<template>
  <div id="app">
    <custom-tshirt></custom-tshirt>
  </div>
</template>

<script>
import CustomTshirt from './components/CustomTshirt.vue'

export default {
  name: 'App',
  components: {
    CustomTshirt
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
