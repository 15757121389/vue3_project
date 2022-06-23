<template>
  <div style="border:2px solid red;margin-top: 10px">
    <h2>我是hello子组件内容</h2>
    <h2>接收父组件的参数:{{message}}</h2>
    <h2>接收父组件的参数:{{list}}</h2>
<!--    单向数据流，子组件的数据改变不影响父组件，父组件改变会传给子组件-->
    <button @click="message='222'">子组件按钮</button>
<!--    <h2>接收父组件的参数:{{aaa}}</h2>-->
  </div>
</template>
<script>
export default {
  // 字符串数组
  // props:['message','aaa']
  // 对象
  props:{
    // 1、类型的限制
    // message: String,
    // aaa: Number
    // 2、除了类型限制，还可以设置默认值,是否必传
    message: {
      // type: [Array,String],
      type: String,
      default:'你好',
      // required: true
    },
    list:{//对象或数组的默认值必须从一个工厂函数返回
      type:Array,
      default(){
        return []
      }
    }

  },
  data(){
    return{
      childMsg:'hello组件的变量'
    }
  },
  mounted() {
    // 访问父组件
    //console.log(this.$parent)
    // 访问根组件
    console.log(this.$root)
  }


}
</script>