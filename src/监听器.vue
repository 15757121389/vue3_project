<script>
 // 声明式渲染，可以提高开发效率
 export default{
   data() {
     return{
       num:0,
       uname:"张三",
       message: "你好",
       user:{
         name:'张三'
       }
     }
   },
   methods: {

   },
   watch: {
     // 每当message发生变化时，该函数将会执行
     // message: function (newValue,oldValue){//一个数据可以影响多个数据
     //   console.log(newValue,oldValue)
     //   //执行异步操作，或者复杂逻辑操作
     //   if(newValue.length<5 || newValue.length>10){
     //     console.log('输入框的内容长度不能小于5或者大于10')
     //   }
     // }
     message:{
       immediate:true,//初始化时就调用监听函数
        handler:function (newValue){
            console.log(newValue)
            //执行异步操作，或者复杂逻辑操作
            if(newValue.length<5 || newValue.length>10){
              console.log('输入框的内容长度不能小于5或者大于10')
            }
        }
     },
     //监听不到对象中的属性变化，需要使用到深度监听
     // user:function (newValue){
     //   console.log(newValue)
     // }
    // user:{
    //    handler:function (newValue){
    //      console.log(newValue)
    //    },
    //   deep:true,//表示是否开启深度监听，开启后将监听对象的所有属性，侦听器会一层层向下遍历，给对象没一个属性都加上侦听器，开销大
    // }
     //使用字符串的形式进行优化，只监听对象里的指定属性
     "user.name":{
       handler:function (newValue){
         console.log(newValue)
       },
       deep:true,//表示是否开启深度监听，开启后将监听对象的所有属性，侦听器会一层层向下遍历，给对象没一个属性都加上侦听器
     }
   }
 }
</script>

<template>
  <div>
    <p>{{num}}</p>
    <p>{{uname}}</p>
    <p>{{message}}</p>
    <button @click="message='你好'">改变message</button>
    <input type="text" v-model="message" />
    <p>{{user.name}}</p>
    <button @click="user.name='李四'">改变对象</button>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
