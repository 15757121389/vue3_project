<script>
import HelloGouzi from "./components/HelloGouzi.vue";
export default{
  data() {
    return{
      isShow:true
    }
  },
  components:{
    HelloGouzi
  },
  // created钩子函数，用来在一个实例被创建后执行代码
  // data methods已经准备好，DOM还没准备好
  created() {
  },
  mounted() {
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
<!--    v-if创建和销毁节点-->
    <HelloGouzi v-if="isShow"></HelloGouzi>
    <button @click="isShow = !isShow">控制hello组件显示</button>
  </div>

</template>

<style>
</style>
