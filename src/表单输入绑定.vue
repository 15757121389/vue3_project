<script>
export default{
  data() {
    return{
      msg:'helloworld',
      checked:"",
      fruits:[],
      sex:"男",
      city:'杭州',
      citys:[],
      count:''
    }
  },
  computed:{
  },
  methods: {
    changeValue(e){
      console.log(e.target.value)
      this.msg = e.target.value
    },
    downmsg(){
      console.log(this.msg)
    }
  },
  watch: {
  }
}
</script>

<template>
  <div>
<!--    v-model基本使用-->
    <input type="text" v-model="msg">
    <h2>{{msg}}</h2>
<!--    v-model的原理-->
<!--本质是两个操作
    1、v-bind绑定一个value属性
    2、v-on给当前元素添加一个input事件-->
    <input type="text" :value="msg" @input="changeValue">

<!--    复选框-->
<!--    单个勾选框，v-model是一个布尔值-->
    <input type="checkbox" v-model="checked">
    <h2>{{checked}}</h2>
<!--    多个勾选框-->
    <input type="checkbox" v-model="fruits" value="苹果">苹果
    <input type="checkbox" v-model="fruits" value="草莓">草莓
    <input type="checkbox" v-model="fruits" value="西瓜">西瓜
    <input type="checkbox" v-model="fruits" value="梨子">梨子
    <h2>喜欢的水果：{{fruits}}</h2>
<!--    单选框-->
    <input type="radio" v-model="sex" value="男">男
    <input type="radio" v-model="sex" value="女">女
    <h2>性别：{{sex}}</h2>
<!--    选项框-->
<!--单选-->
    <select name="" id="" v-model="city">
      <option value="杭州">杭州</option>
      <option value="北京">北京</option>
      <option value="黄山">黄山</option>
    </select>
    <h2>城市：{{city}}</h2>
<!--多选 按住ctrl或者鼠标按住拖动-->
    <select name="" id="" v-model="citys" multiple>
      <option value="杭州">杭州</option>
      <option value="北京">北京</option>
      <option value="黄山">黄山</option>
    </select>
    <h2>城市：{{citys}}</h2>
<!--v-model修饰符的使用-->
<!--    .lazy  输入框失去焦点后同步数据-->
    <input type="text" v-model.lazy="msg">
    <h2>{{msg}}</h2>
    <!--    .number  输入框默认都当做字符串处理，使用.number输入内容转为数字类型-->
    <input type="text" v-model.number="count">
    <h2>{{typeof count}}</h2>
    <!--    .trim  自动过滤用户输入的首尾空白字符-->
    <input type="text" v-model.trim="msg" @keydown="downmsg">
    <h2>{{msg}}</h2>
  </div>

</template>

<style>
</style>
