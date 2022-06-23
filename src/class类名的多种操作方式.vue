<script>
 // 声明式渲染，可以提高开发效率
 export default{
   data() {
     return{
       message: 'helloworld',
       isActive:true,
       error:null,
       classObj:{
         active:true,
         helloworld: true
       },
       activeClass:'active'
     }
   },
   computed:{
     classObjCom:function (){
      return{
        active:this.isActive  && !this.error,
        helloworld: this.error
      }
     }
   },
   methods: {

   },
   watch: {
   }
 }
</script>

<template>
  <div>
<!--第一种，放置字符串-->
    <p class="active">hello</p>
<!--第二种，放置对象（常用）-->
<!--<p :class="{类名:boolean}">hello1</p>-->
    <p :class="{active:isActive}">hello1</p>
    <p :class="{active:isActive,helloworld:isActive}">hello1</p>
<!--    数据对象可以放在data里-->
    <p :class="classObj">hello2</p>
    <button @click="isActive=!isActive">改变active</button>
<!--    动态类和普通类同时存在，不会起冲突，会合并-->
    <p :class="{active:isActive}" class="helloworld">hello1</p>
<!--第三种，使用computed-->
    <p :class="classObjCom">hellocomputed</p>
<!--    第四种，数组语法(不常用)，操作不灵活-->
  <p :class="[message,activeClass]">数组语法</p>
<!--    数组和对象结合使用-->
<p :class="[message,{active:true}]">数组和对象结合</p>
  </div>
</template>

<style>
.active{
  font-size: 20px;
  color: blue;
}
.helloworld{
  background-color: red;
}
</style>
