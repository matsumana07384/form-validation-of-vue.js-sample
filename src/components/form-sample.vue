<template>
<div id="countup">
  <p>{{ count }} 回クリックしたよ</p>
  <button v-on:click="increment">カウントするよ</button>
</div>
</template>
<script>
export default {
  el:'#countup',
  data:{
    count: 0
  },
  methods:{
    increment: function() {
      this.count +=1
    }
  }
}
</script>
<style scoped>

</style>
