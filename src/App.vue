<template>
  <div>
    <h2 v-show="info">我是v-show</h2>
    <h2 v-if="str">我是v-if</h2>
    <h2 v-if="age >= 18">成年了</h2>
    <h2 v-else>未成年</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      info: true,
      str: true,
      age: 2,
    };
  },
};
</script>

<style>
</style>
