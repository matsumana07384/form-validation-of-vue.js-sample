<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <hr>
    <loginForm title="ログインフォーム"></loginForm>
    <hr>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import loginForm from './components/LoginForm.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    loginForm
  },
    data: function() { 
    return {
      loginForm:{
        loginId:null,
        passWWord:null,
      },
      Validation:{
        loginReult: "",
        passWordReult:"",
      },
    }
  },
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
