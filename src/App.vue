<template>
  <Title msg="Une application simple"/>
  <Controller/>
</template>

<script>
import Title from './components/Title.vue'
import Controller from './components/Controller.vue'

export default {
  name: 'App',
  components: {
    Title,
    Controller
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
}
</style>
