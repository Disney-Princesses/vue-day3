<template>
  <div>
    <!-- 动态绑定style 语法 v-bind:style="对象" 
  			v-bind:style = '{css属性名: 值}'-->
    <p v-bind:style="{ color: 'pink', fontSize: '60px' }">vue 动态绑定style11</p>
    <p :style="{ color: changeColor, fontSize: size }">vue 动态绑定style22</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      changeColor: 'green',
      size: '60px'
    }
  },
  methods: {


  }
}
</script>
<style>
</style>