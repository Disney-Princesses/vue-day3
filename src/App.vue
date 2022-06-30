<template>
  <div>
    <p :class="{ active: arr }" class="box">我是p标签</p>
    <button @click="checked">点击改变</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: true,
    };
  },
  methods: {
    checked() {
      this.arr = !this.arr;
    },
  },
};
</script>

<style >
.active {
  color: red;
}
.box {
  border: 5px solid yellow;
}
</style>