<template>
  <div>
    <p><b>{{title}}</b></p>
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
        <p class="error">
          {{ Validation.loginReult }}
        </p>
        <span>Password: </span>
        <input 
          type="password"
          placeholder="8 or more characters"
          v-model="loginForm.passWord"
          >
        <p>
          Input Password is {{ loginForm.passWord }}
        </p>
        <p class="error">
            {{ Validation.passWordReult }}
        </p>
        <button v-on:click="checkFrom">
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
        passWord:null,
      },
      Validation:{
        loginReult: "",
        passWordReult:"",
      }
    }
  },
methods: {
    checkFrom: function(event){
      var LoginId = false
      var PassWord = false
      
    //IDの入力フォームのバリデーション
      if (!this.loginForm.loginId) {
        this.Validation.loginReult="ログインIDを入力してください"
      } 
      else if(!this.checkString(this.loginForm.loginId)){
        this.Validation.loginReult="半角英数で入力してください"
      }else {
        LoginId = true
      }

    //パスワードの入力フォームのバリデーション
      if (!this.loginForm.passWord){
          this.Validation.passWordReult="パスワードを入力してください"
        }
        else if (!this.checkMaxCount(this.loginForm.passWord)){
          this.Validation.passWordReult="8文字以上を入力してください"
        } 
        else if (!this.validPassword(this.loginForm.passWord)){
          this.Validation.passWordReult="英数字記号を1つずつ入力してください"
          }
        else {
          PassWord=true
        }
      if(LoginId == true && PassWord == true){
        this.Validation.loginReult=""
        this.Validation.passWordReult=""
        alert('Hello,' + this.loginForm.loginId + '!');
      } 
      event.preventDefault() 
    },
    checkString: function(inputdata){
      var re = /^[A-Za-z0-9]*$/
      return re.test(inputdata);
    },
    checkMaxCount: function(inputdata){
      var re = /(?=^.{8,}$)/i
      return re.test(inputdata);
    },
    validPassword: function (inputdata) {
      var re = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!-/:-@[-`{-~])[!-~]{8,48}$/i
      return re.test(inputdata);
    }
  }
}
</script>

<style scoped>
.error { color: red; }
</style>