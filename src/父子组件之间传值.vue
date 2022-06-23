<script>
import Content from './components/父子组件访问Content.vue'
export default{
  data() {
    return{
      msg:''

    }
  },
  components:{
    Content
  },
  computed:{
  },
  methods: {
    getChildMsg(value){
      this.msg = value
      console.log(value+'子组件的传值')
    }
  },
  watch: {
  }
}
</script>

<template>
  <div>
<!--    拿到子组件content的数据，通过自定义事件-->
<!--    2、在父组件中，通过v-on监听子组件中的自定义事件-->
    <Content @injectMsg="getChildMsg"></Content>
    <h2>{{msg}}</h2>
  </div>
</template>

<style>
</style>
