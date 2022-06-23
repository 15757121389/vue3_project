<template>
  <div style="border:1px solid green;padding: 5px">
    <FirstComponent></FirstComponent>
  </div>
</template>

<script>
  //详情见FirstComponent ThirdComponent
import FirstComponent from "./components/FirstComponent.vue";
export default {
  data(){
    return{

    }
  },
  components:{
    FirstComponent
  }
}
</script>

<style>

</style>