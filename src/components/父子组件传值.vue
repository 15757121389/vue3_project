<template>
  <div>
    <Hello :message="msg" :list="list"></Hello>
    <h2>我是content组件内容</h2>
<!--    组件是带有名称的可复用的实例，单独功能模块的封装-->
    <h2>{{msg}}</h2>
    <button @click="msg='你好'">改变msg</button>
    <button @click="sendParent">提交数据给父组件</button>
  </div>
</template>
<script>
// const obj = {
//   msg:'helloworld'
// }
import Hello from './Hello.vue'
export default {
  components:{
    Hello
  },
  // data必须是一个函数，并且返回对象
  // 函数有局部作用域，每个组件都是返回新的对象，组件复用不会有数据污染
  data() {
    return{
      msg:'123',
      list: [1,2,3,4]
    }
    // return obj
  },
  methods: {
    // 1、在子组件中通过$emit来触发事件
    sendParent(){
      // this.$emit('自定义事件的名称','发送的事件参数')
      this.$emit('injectMsg',this.msg)
    }
  }
}
</script>