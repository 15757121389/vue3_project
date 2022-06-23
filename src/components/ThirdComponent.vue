<template>
<div style="border:1px solid red;padding: 5px">
  <h2>Third组件内容</h2>
<!--  <p>跨级通信获取的内容：{{obj.message}}</p>-->
  <p>{{newMsg}}</p>
</div>
</template>

<script>
export default {
name: "ThirdComponent.vue",
data(){
  return{

  }
},
  computed:{
  newMsg(){
    return this.message()
  }
  },
  // 孙组件跨级获取数据
  inject:['message']
  // inject:['obj']
}
</script>

<style scoped>

</style>