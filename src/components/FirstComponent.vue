<template>
<div>
  <h2>我是第一层子组件</h2>
  <SecondComponent></SecondComponent>
</div>
</template>

<script>
import SecondComponent from "./SecondComponent.vue";
export default {
  name: "FirstComponent.vue",
  components:{
    SecondComponent
  }
}
</script>

<style scoped>

</style>