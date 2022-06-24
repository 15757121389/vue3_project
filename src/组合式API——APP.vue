<script>
import HelloGouzi from "./components/HelloGouzi.vue";
import {ref,reactive,toRefs} from 'vue'
export default{
  data() {
    return{
      message:'hello'
    }
  },
  //组合式API，将同一个逻辑关注点相关代码收集在一起
  beforeCreate() {
    console.log('beforeCrete')
  },
  created() {
    console.log('created')
  },
  setup(){//组件创建前执行,因此不要使用this,this不会指向实例
    console.log('setup')


    let msg='你好'
    console.log(msg)
    function changeMsg(){
      msg = '你好呀'
      console.log(msg)//数据不是响应式
    }


    //通过ref来定义响应式变量
    let counter = ref(0) //ref()是一个函数，返回带有value属性的对象
    function changeCounter(){
      counter.value++
    }

    //通过reactive来定义引用类型的数据
    //obj的逻辑代码
    const obj=reactive({
      name:'张三',
      age:18,
      children:{
        name:'小张'
      }
    })
    function changeObj(){
      obj.name='李四'
    }
    //通过ES6扩展运算符解构 会使对象中的属性不是响应式
    // toRefs()使解构后的数据重新获得响应式
    let {name,children} = toRefs(obj)
    return {msg,changeMsg,counter,changeCounter,changeObj,obj,name,children}
    // return {msg,changeMsg,counter,changeCounter,changeObj,obj,...toRefs(obj),name,children}
  },

  components:{
    HelloGouzi
  },
  computed:{
  },
  methods: {
  },
  watch: {
  }
}
</script>

<template>
  <div>
    <h2>{{msg}}</h2>
    <button @click="changeMsg">改变setup的msg</button>
<!--    模板会自动解析value值-->
    <h2>counter{{counter}}</h2>
    <button @click="changeCounter">改变setup的counter</button>

    <h2>children{{obj.children.name}}</h2>
    <h2>children直接{{children.name}}</h2>
    <h2>obj{{obj.name}}</h2>

    <h2>obj直接{{name}}</h2>
    <button @click="changeObj">改变obj</button>
<!--    <HelloGouzi></HelloGouzi>-->
  </div>

</template>

<style>
</style>
