<template>
  <div>
    <li v-for="(item, index) in arr" :key="item">
      <span>{{ item }}</span>
      <button @click="delFn(index)">删除</button>
    </li>
    <br>
    <button @click="addNum">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 5, 3]
    }
  },
  methods: {
    addNum() {
      this.arr.push(Math.floor(Math.random() * 10))
    },
    delFn(index) {
      this.arr.splice(index, 1)
    }
  }

}
</script>

<style>
</style>