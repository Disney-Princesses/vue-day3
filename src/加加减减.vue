<template>
  <div id="app">
    <ul>
      <li v-for="(item, index) in myArr" :key="index">
        {{ item }} <button @click="delFn(index)">删除</button>
      </li>
    </ul>
    <button @click="addFn">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myArr: [1, 2, 3],
    };
  },
  methods: {
    addFn() {
      const num = Math.floor(Math.random() * 10);
      this.myArr.push(num);
    },
    delFn(index) {
      this.myArr.splice(index, 1);
    },
  },
};
</script>

<style >
.red {
  color: red;
}
</style>