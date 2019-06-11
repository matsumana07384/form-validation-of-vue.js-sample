<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SampleData></SampleData>
    <!-- <Form title="ID" formType="text"></Form>
    <Form title="Password" formType="password"></Form>
    <Button buttonLabel="確認する"></Button>
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Form from './components/form.vue'
import Button from './components/button.vue'
import SampleData from './components/form-sample.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Form,
    Button,
    SampleData
  },
  methods:{

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
