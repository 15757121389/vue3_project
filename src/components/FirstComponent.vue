<template>
<div style="border:1px solid orange;padding: 5px">
  <h2>我是第一层子组件</h2>
<!--  <button @click="obj.message='你好'">改变msg</button>-->
  <button @click="message='你好'">改变msg</button>
<!--  <p>{{obj.message}}</p>-->
  <p>{{message}}</p>
  <SecondComponent></SecondComponent>
</div>
</template>

<script>
import SecondComponent from "./SecondComponent.vue";
export default {
  name: "FirstComponent.vue",
  components:{
    SecondComponent
  },
  data(){
    return{
      message:'helloworld',
      obj:{
        message:'helloworld'
      }
    }
  },
  // provide/inject不是响应式的   prop是响应式的单项数据流
  // provide:{
  //   // provide里不能推送实例属性，会报错
  //   // message:this.message
  // 只能传固定的值
  //   message:'helloworld'
  // }

  // 如果想要传送实例属性,使用函数形式
  provide(){
    return {
      // message: this.message
      // obj:this.obj//响应式对象方式来完成单项数据流
      message:()=>this.message //函数返回响应式数据
    }
  }

}
</script>

<style scoped>

</style>