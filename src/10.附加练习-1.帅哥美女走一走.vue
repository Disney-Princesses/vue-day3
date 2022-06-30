<template>
  <div>
    <li v-for="item in arr" :key="item">{{item}}</li><br>
    <button @click="moveFn">走一走</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: ['小哥哥', '小姐姐', '程序员']
    }
  },
  methods:{
    moveFn() {
      this.arr.push(this.arr[0])
      this.arr.shift()
    }
  }

}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
li {
  font-size: 20px;
  line-height: 35px;
}
</style>