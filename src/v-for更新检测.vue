<template>
  <div>
    <ul>
      <li v-for="item in arr" :key="item">{{ item }}</li>
    </ul>
    <button @click="revBtn">点击翻转</button>
    <button @click="sliceBtn">截取前三个</button>
    <button @click="upDataBtn">更新第一个元素</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 2, 3, 4, 5],
    };
  },
  methods: {
    revBtn() {
      this.arr.reverse();
    },
    sliceBtn() {
      this.arr = this.arr.slice(0, 3);
    },
    upDataBtn() {
      this.$set(this.arr, 0, 100);
    },
  },
};
</script>

<style >
</style>