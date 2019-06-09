<template>
<div id="appform">
  <form>
      <div v-if="formType==='password'">
      <span>{{ title }} : </span>
      <br>
        <input
          type="password"
          placeholder="password"
          v-model="inputPass"
          >
          <p> Inputting Password is {{ inputPass }} </p>
      </div>
      <div v-else>
      <span>{{ title }} : </span>
      <br>
        <input 
          type="text"
          v-model="message"
          placeholder="edit me"
        >
      </div>
  </form>
</div>
</template>

<script>
import { StringDecoder } from 'string_decoder';
export default {
  // name: 'Form',
  el:'#appform',
  props: {
    'title': {
      type: String,
      default: '' 
    },
    'formType': {
      type: String,
      default: 'text' ,
      required: true
    }
  },
  data:{
    // inputPass: 'パスワード',
    // inputText: '入力値',
    errors: [],
    name: null,
    email: null,
    movie: null
  }
}
</script>

<style scoped>
</style>
