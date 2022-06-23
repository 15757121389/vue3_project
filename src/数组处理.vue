<script>
export default{
  data() {
    return{
      array:[1,2,3,4,5]
    }
  },
  computed:{
  },
  methods: {
changeList() {
  // vue2通过索引值去修改数组，不会实现视图更新，vue3可以
  // this.array[5]=7
  // push();给数组末尾添加元素
  // this.array.push(7,8,9)
  // pop();删除数组的最末尾元素
  // this.array.pop()
  // shift();删除数组的第一位
  // this.array.shift()
  // unshift();从数组的首位开始添加元素
  //   this.array.unshift(1,2,3)
  // splice();删除元素、插入元素、替换元素
  // 第一个参数表示开始插入或者删除的位置下标（包括）,必选
  // 删除
  // 第二个参数表示要删除个数，如果没有传，表示删除后面所有的元素
  // this.array.splice(1,2)
  // this.array.splice(1)
  //插入
  //第二个参数传入0，第三个参数表示要插入的元素
  // this.array.splice(1,0,7,8,9)
  // 替换元素
  // 第二个参数表示要替换几个元素，第三个参数表示替换的元素
  // 原理是先删除，然后插入第三个参数的元素
  // this.array.splice(1,3,7,8)
  // sort();排序 默认从小到大
  // this.array.sort()
  // 倒序
  // this.array.sort(function (a,b){return b-a})
  // reverse();翻转
  this.array.reverse();


}
  },
  watch: {
  }
}
</script>

<template>
  <div>
<ul>
  <li v-for="item in array" :key="item">
    {{ item }}
  </li>
</ul>
    <button @click="changeList">改变数组</button>
  </div>
</template>

<style>
</style>
