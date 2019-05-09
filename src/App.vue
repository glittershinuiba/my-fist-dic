<template>
  <div id="app">
  <img height="200" alt="supportocat holding envelope" src="https://github.githubassets.com/images/modules/octocats/supportcat.jpg">
   <Input />
   
      
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Input from './components/Input.vue' 

export default {
  name: 'app',
  components: {
    HelloWorld,
    Input
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
