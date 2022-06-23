<template>
<div style="border:1px solid blue;padding: 5px">
  <h2>second组件内容</h2>
  <ThirdComponent></ThirdComponent>
</div>
</template>

<script>
import ThirdComponent from "./ThirdComponent.vue";
export default {
name: "SecondComponent.vue",
  components:{
    ThirdComponent
  }
}
</script>

<style scoped>

</style>