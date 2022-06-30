<template>
  <div id="app">
    <div v-for="(item, index) in arr" :key="item" :class="{ box: true }">
      <input
        type="checkbox"
        name=""
        :id="index"
        :value="item"
        v-model="numAll"
      />
      <span> {{ item }} </span>
    </div>
    <div>总价格为:{{ dataAll }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      numAll: [],
    };
  },
  computed: {
    dataAll() {
      return this.numAll.reduce((pre, item) => {
        return (pre += item);
      }, 0);
    },
  },
};
</script>

<style>
html {
  font-size: 20px;
}
.box {
  display: inline-block;
  width: 50px;
  height: 50px;
  /* padding: 0, 10px; */
}
input {
  width: 15px;
  height: 15px;
}
#app {
  margin: 100px 200px;
}
</style>