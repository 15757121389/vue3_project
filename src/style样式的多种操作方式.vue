<script>
export default{
  data() {
    return{
      activeColor: 'red',
      activeFontSize:'30px',
      activebgcolor: 'blue',
      styleObj:{
        color: 'red',
        fontSize:'30px',
        'background-color': 'blue'
      }
    }
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
    <!--    使用内联样式-->
    <!--第一种，放置字符串-->
    <p style="color: red;font-size: 20px">hello</p>
    <!--    第二种，放置对象,驼峰命名或者短线分隔（用''）-->
    <!--    <p style="{key(css属性名):value(属性值，来自data中定义的值)}"></p>-->
    <!--    常常结合返回对象的属性和计算属性一起使用-->
    <p :style="{color: activeColor,fontSize: activeFontSize,'background-color':activebgcolor}">hello1</p>
    <p :style="styleObj">hello2</p>
    <!--    第三种数组语法-->
    <p :style="[styleObj,{border:'5px solid orange'}]">hello3</p>

  </div>
</template>

<style>
</style>

