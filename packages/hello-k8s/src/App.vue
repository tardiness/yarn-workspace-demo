<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <hello-k8s msg="hello k8s"></hello-k8s>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HelloK8s from './components/HelloK8s.vue'
import {docker} from 'hello-docker'

export default {
  name: 'App',
  components: {
    HelloWorld,
    HelloK8s,
  },
  mounted() {
    console.log(docker.msg)
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
