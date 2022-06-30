<template>
  <div id="app">
    <ul>
      <li v-for="(item, index) in arr" :key="item">
        <span>{{ item }}</span>
        <button @click="delFn(index)">删除</button>
      </li>
    </ul>
    <button @click="addFn">生成</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arr: [1, 3, 4, 5],
    };
  },
  methods: {
    addFn() {
      this.arr.push(Math.floor(Math.random() * 20));
    },
    delFn(index) {
      this.arr.splice(index, 1);
    },
  },
};
</script>
