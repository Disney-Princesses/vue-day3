<template>
  <div id="app">
    <ul>
      <li v-for="item in myArr" :key="item">{{ item }}</li>
    </ul>
    <button @click="addFn">点击动一动</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myArr: ["帅哥", "美女", "程序猿"],
    };
  },
  methods: {
    addFn() {
      this.myArr.push(this.myArr[0]);
      this.myArr.shift();
    },
  },
};
</script>

<style >
.red {
  color: red;
}
</style>