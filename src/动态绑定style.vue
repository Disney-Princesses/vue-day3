<template>
  <div>
    <p :style="{ color: 'pink', fontSize: '60px' }">动态绑定style</p>
    <p :style="{ color: temp, fontSize: navs + 'px' }">动态绑定style123</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navs: 50,
      temp: "yellow",
    };
  },
  methods: {},
};
</script>

<style >
ul {
  list-style: none;
  border-radius: 10px;
  width: 400px;
  overflow: hidden;
  padding: 0;
}
ul li {
  float: left;
  width: 100px;
  height: 40px;
  background-color: #ccc;
  color: #fff;
  text-align: center;
  line-height: 40px;
  cursor: pointer;
}
li.active {
  background-color: blue;
}
</style>