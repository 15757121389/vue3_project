<script>
export default{
  data() {
    return{
      age: 0,
      sex:'man'
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
<!--    v-if-->
    <input type="text" v-model="age">
    <h1 v-if="age>18">我是成年人了</h1>
    <h1 v-else-if="age==18">我今天刚好成年</h1>
    <h1 v-else>我还是个小孩</h1>
<!--    在 <template> 元素上使用 v-if 条件渲染分组,template不会被渲染，div渲染-->
    <template v-if="age>=18">
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
    </template>
    <div v-if="age>=18">
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
      <p>你好</p>
    </div>
<!--    v-show-->
<!--    v-show的元素会始终渲染，并保留在DOM中，只是display属性为none-->
<!--    v-show不支持template元素，也不支持v-else-->
<!--    v-if有更高的切换开销，v-show有更高的初始渲染开销，如果需要频繁切换，使用v-show较好，如果运行时条件很少改变或者一次性渲染，则使用v-if较好-->
    <p v-show="sex=='man'">男生</p>
    <p v-show="sex=='woman'">女生</p>
  </div>
</template>

<style>
</style>
