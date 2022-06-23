<script>
import Content from './components/Content.vue'
export default{
  data() {
    return{
      msg:'hello'

    }
  },
  components:{
    Content,
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
<!--    如果有多个值，同时放到组件中进行替换，一起作为替换元素-->
    <Content><button>插槽按钮</button><h2>标题</h2></Content>
<!--    指定位置替换，具名插槽-->
<!--    vue2通过标签上slot="名字"   vue3通过template上的v-slot:名字-->
<!--    插槽的数据和父组件同步-->
<!--    父级模板里的所有内容都是在父级作用域中编译；子模版里的所有内容都是在子作用域中编译的-->

    <Content>
      <template v-slot:input><input type="text"></template>
      <template v-slot:button><button @click="msg='000'">按钮{{msg}}</button></template>
      <template v-slot:h2>标题</template>
    </Content>
<!--    使用子组件的数据-->
<!--    作用域插槽，父组件替换插槽的标签，但是插槽的数据是由子组件提供-->
<!--    无序列表-->
    <Content>
<!--      接收子组件插槽传输过来的数据   v-slot:插槽名字（无名字就是default）="slotProps"   slotProps中包含所有传过来的属性-->
      <template v-slot:default="slotProps">
        <ul>
          <li v-for="item in slotProps.list" :key="item">
            {{ item }}
          </li>
        </ul>
      </template>
    </Content>
<!--    有序列表-->
    <Content>
      <template v-slot:default="slotProps">
        <ol>
          <li v-for="item in slotProps.list" :key="item">{{item}}</li>
        </ol>
      </template>
    </Content>
  </div>
</template>

<style>
</style>
