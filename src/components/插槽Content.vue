<template>
  <div>
    <h2>我是content组件内容</h2>
    <div>
<!--      <slot></slot>-->
<!--      <button>默认按钮</button>为备用内容，父组件没有提供内容时渲染-->
      <!--      如果有多个插槽，可以给插槽命名-->
<!--      <slot name="button"><button>默认按钮</button></slot>-->
<!--      <slot name="input"><input type="text" placeholder="备用输入框"></slot>-->
<!--      <slot name="h2"></slot>-->
<!--      子组件插槽的数据传输到父组件-->
      <slot :list="list" :name="name"></slot>

    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      msg:'你好',
      name:'张三',
      list:[1,2,3,4,5,6]
    }
  }
}
</script>