<template>
  <div>
    <!-- 语法:
    * v-text="vue数据变量"    
    * v-html="vue数据变量" 注意: 两者会覆盖插值表达式-->
    <!-- 插值表达式不解析标签 -->
    <h2>{{str}}</h2>
    <!-- v-text把值当成普通字符串显示 -->
    <h2 v-text="str"></h2>
    <!-- v-html把值当做html解析 -->
    <h2 v-html="str"></h2>
    <!-- <h2 v-html="str">{{str}}</h2> -->
  </div>
</template>

<script>
export default {
  data(){
    return {
     str: "<span>我是一个span标签</span>"
    }
  },
  methods: {
  
  }
}
</script>