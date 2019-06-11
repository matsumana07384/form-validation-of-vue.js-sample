<template>
  <button>{{buttonLabel }}</button>
</template>
<script>
export default {
  props: {
    'buttonLabel' :{
      type: String,
      default: 'send',
      required: true
    }
  }
}
</script>
<style scoped>

</style>
