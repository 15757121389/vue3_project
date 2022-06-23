<script>
export default{
  data() {
    return{
      person:['张三','李四','王五'],
      array:[
        {name:'张三',grade:90},
        {name:'李四',grade:80},
        {name:'王五',grade:60},
      ],
      personObj:{
        name:'张三',
        age:18,
        sex:'man'
      }
    }
  },
  computed:{
  },
  methods: {
    addPerson() {
      this.array.unshift({name:'赵六',grade:60})
    }

  },
  watch: {
  }
}
</script>

<template>
  <div>
    <!--    v-for使用数组，item代表数组中每个元素，index代表索引、下标-->
    <ul>
      <li v-for="(item,index) in array" :key="index">{{item.name}}--{{index}}</li>
    </ul>
    <!--    of代替in效果一样-->
    <ul>
      <li v-for="(item,index) of array" :key="index">{{item.name}}--{{index}}</li>
    </ul>
    <!--    v-for使用对象，三个参数，按顺序，item代表对象每个属性值，key代表每个属性名,index表示索引-->
    <ul>
      <li v-for="(item,key,index) in personObj" :key="index">{{item}}--{{key}}--{{index}}</li>
    </ul>
    <!--    为了给 Vue 一个提示，以便它能跟踪每个节点的身份，从而重用和重新排序现有元素-->
    <!--    key：列表项的唯一标识-->
    <!--    快速找到节点，减少渲染次数，提高渲染性能-->
    <ul>
      <li v-for="(item,index) in array" :key="item.name"><input type="checkbox">{{item.name}}-->{{index}}</li>
    </ul>
    <button @click="addPerson">增加数组元素</button>
  </div>
</template>

<style>
</style>
