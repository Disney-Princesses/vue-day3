<template>
  <div>
    <div
      v-for="(item, index) in arr"
      style="display: inline-block"
      :key="index"
    >
      <input type="checkbox" v-model="newArr" :value="item" />
      <span>{{ item }}</span>
    </div>
    <p>你选中的元素, 累加的值和为: {{ sumFn() }}</p>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],

      newArr: [],
    };
  },
  methods: {
    sumFn() {
      return this.newArr.reduce((count, val) => {
        return (count += val);
      }, 0);
    },
  },
};
</script>

<style></style>
