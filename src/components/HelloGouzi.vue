<template>
<div>helloworld</div>
  <h2>{{count}}</h2>
  <button @click="count++">改变msg</button>
</template>

<script>
export default {
  name: "HelloGouzi.vue",
  data(){
    return{
      count:0
    }
  },

  //生命周期函数（钩子函数）
  beforeCreate() {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    console.log('mounted')
  },
  // 页面内容发生改变会调用，如果仅是数据改变则不会调用
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated() {
    console.log('updated')
  },
  beforeUnmount() {
    console.log('beforeUnmount')
  },
  unmounted() {
    console.log('unmounted')
  }


}
</script>

<style scoped>

</style>