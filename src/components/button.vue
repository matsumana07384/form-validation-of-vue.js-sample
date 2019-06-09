<template>
  <button>{{buttonLabel }}</button>
</template>
<script>
export default {
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
