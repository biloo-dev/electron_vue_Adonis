<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <pre>{{ users.data }}</pre>
    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      users : []
    }
  },
  async mounted(){
    try {
     this.users=  await axios('http://127.0.0.1:3333/api/users');
    } catch (err) {
      console.log('err :>> ', JSON.stringify(err));
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
  color: #2c3e50; 
}
</style>
