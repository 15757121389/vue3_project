<template>
  <div>
<!--    父子组件的访问方式-->
<!--    父组件访问子组件 vue3用$refs  vue2用$children 返回数组类型 有缺陷-->
<!--    ref:给元素或者子组件注册引用信息-->
<!--    子组件访问父组件 $parent  因为组件复用性很高，父组件经常变动，在开发中尽量少用，使用props来传值更合适-->
<!--    子组件访问根组件$root-->
    <Hello :message="msg" :list="list" ref="hello"></Hello>
    <h2>我是content组件内容</h2>
    <h2>{{msg}}</h2>
    <button @click="msg='你好'">改变msg</button>
    <p ref="p">1233</p>
  </div>
</template>
<script>

import Hello from './Hello.vue'
export default {
  components:{
    Hello
  },

  data() {
    return{
      msg:'123',
      list: [1,2,3,4]
    }
  },
  methods: {

  },
  mounted() {
    // console.log(this.$refs.hello.childMsg)
    // console.log(this.$refs)
  }
}
</script>