<template>
<div>
  <p>{{title}}</p>
  <form
  v-on:submit.prevent="onSubmit"
  >
    <span>ID : </span>          
    <input
      type="text"
      placeholder="input your id"
      v-model="loginForm.loginId"
      >
      <p>
        Input loginId is {{ loginForm.loginId }} 
      </p>
      <p>
        {{ Validation.loginReult }}
      </p>
      <span>Password: </span>
      <input 
        type="password"
        placeholder="8 or more characters"
        v-model="loginForm.passWWord"
        >
      <p>
        Input Password is {{ loginForm.passWWord }}
      </p>
      <p>
        {{ Validation.passWordReult }}
      </p>
      <button v-on:click="checkForm">
        送信する
      </button>
    </form>
</div>
</template>

<script>
export default {
  props: {
      title : String
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
      }
    }
  },
methods: {
    checkForm: function(event){
      if(
        this.loginForm.loginId !=null
        &&
        this.loginForm.passWWord != null
        ){
        this.Validation.loginReult=""
        this.Validation.passWordReult=""
        alert('Hello,' + this.loginForm.loginId + '!');
      } else {

      if (!this.loginForm.loginId) {
        this.Validation.loginReult="ログインIDを入力してください"
      }

      if (!this.loginForm.passWWord){
        this.Validation.passWordReult="パスワードを入力してください"
      }
      else if (!this.checkMaxCount(this.loginForm.passWWord)){
        this.Validation.passWordReult="8文字以上を入力してください"
      } 
      else if (!this.validPassword(this.loginForm.passWWord)){
        this.Validation.passWordReult="英数字記号を1つずつ入力してください"
        }
      }
      event.preventDefault() 
    },
    checkMaxCount: function(inputdata){
      var re = /^[a-z\d]{8,100}$/i
      return re.test(inputdata);
    },
    validPassword: function (inputdata) {
      var re = /^(?=.*?[a-z])(?=.*?\d)[a-z\d]{8,100}$/i
      return re.test(inputdata);
    }
  }
}
</script>

<style scoped>
</style>
