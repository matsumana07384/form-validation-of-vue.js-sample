<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <hr>
    <div class="form">
      <form>
        <span>ID : </span>          
          <input
            type="text"
            placeholder="input your id"
            v-model="loginId"
            >
      </form>
        <p> loginId is {{ loginId }} </p>
      <form>
        <span>Password: </span>
          <input 
            type="password"
            placeholder="edit me"
            v-model="passWWord"
          >
      </form>
        <p>Input Password is {{passWWord}}</p>
    </div>
    <hr>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
  },
  data: function() { 
    return {
      //値の初期化
      loginId:'',
      passWWord:''
    }
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
