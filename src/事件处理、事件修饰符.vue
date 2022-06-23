<script>
export default{
  data() {
    return{
      counter:0,
      age:18
    }
  },
  computed:{
  },
  methods: {
    // countAdd(number) {
    //   this.counter +=number
    // },
    // 没有参数时 e为事件,形参
    // countAdd(e) {
    //   this.counter ++
    //   console.log(e)
    // }
    //接收参数和事件对象
    countAdd(number,e) {
      this.counter +=number
      console.log(e)
    },
    ageAdd(){
      this.age++
    },
    divClick() {
      console.log("父元素的展示")
    },
    btnClick(){
      console.log("子元素的展示")
    },
    submitClick() {
      console.log('数据提交成功')
    },
    btnClickOne() {
      console.log('触发一次')
    },
    keyUp(){
      console.log('键盘被按下了，数据提交成功')
    }
  },
  watch: {
  }
}
</script>

<template>
  <div>
<!--    绑定事件到整个元素-->
<!--    直接通过js代码处理-->
    <h2 @click="counter++">{{ counter }}</h2>
<!--    通过函数,没有传递参数，或者传递事件-->
    <h2 @click="countAdd">{{ counter }}</h2>
<!--    传递参数-->
    <h2 @click="countAdd(5)">{{ counter }}</h2>
<!--    传递参数，又传递事件对象-->
    <h2 @click="countAdd(5,$event)">{{ counter }}</h2>
<!--一个事件，绑定多个处理函数-->

    <h2 @click="countAdd(5),ageAdd()">{{ counter }}--{{age}}</h2>
<!--    事件修饰符 -->
<!--    鼠标点击事件-->
<!--    .stop  阻止子元素的事件冒泡-->
    <div @click="divClick">
      <button @click="btnClick">按钮</button>
      <button @click.stop="btnClick">按钮</button>
    </div>
<!--.prevent  阻止默认行为-->
    <form action="">
      <input type="submit" value="提交" @click.prevent="submitClick">
    </form>
<!--    .once 只触发一次回调-->
    <button @click.once="btnClickOne">只触发一次once</button>
<!--    按键修饰符-->
<!--    .{keyCode(键盘编码) | keyAlias(键盘简写)} 监听键盘的某一个键帽-->
<!--    所有按键按下后会触发-->
    <input type="text" @keyup="keyUp">
<!--    enter键按下后触发-->
    <input type="text" @keyup.enter="keyUp">
  </div>

</template>

<style>
</style>
