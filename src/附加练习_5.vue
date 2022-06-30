<template>
  <div>
    <!-- 无id时, 可以使用index(反正也是就地更新) -->
    <div
      style="display: inline-block"
      v-for="(item, index) in arr"
      :key="index"
    >
      <input type="checkbox" v-model="newArr" :value="item" />
      <span>{{ item }}&nbsp;&nbsp;</span>
    </div>
    <p>你选中的元素, 累加的值和为: {{ theSum() }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      newArr: [],
    };
  },
  methods: {
    theSum() {
      return this.newArr.reduce((pre, cur) => pre + cur, 0);
    },
  },
};
</script>

<style></style>
