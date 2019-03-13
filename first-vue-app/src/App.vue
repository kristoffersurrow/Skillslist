<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png"/>
    <div class="spacer"></div>
    <Skills message ="First-Vue-App"/>
  </div>
</template>


<script>
import Skills from './components/Skills.vue'

export default {
  name: 'app',
  components: {
    Skills
  }
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.spacer {
  height: 50px;
}
.logo{
  width: 200px;
  height: 200px;
  padding: 50px;
  float: right
}
</style>
