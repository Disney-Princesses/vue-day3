<template>
  <div>
    <p v-text="str"></p>
    <p v-html="str"></p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      str: "<h2>我是一个span标签</h2>",
    };
  },
};
</script>

<style>
</style>
