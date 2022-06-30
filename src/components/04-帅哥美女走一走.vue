<template>
  <div id="app">
    <ul>
      <li v-for='item in myArr' :key='item'>{{item}}</li>
    </ul>
    <button @click='clickFn'>走一走</button>
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
   clickFn(){
    // this.myArr.push(this.myArr[0]);
    // this.myArr.shift();//数组的shift()方法是用来删除数组的第一个元素的
    this.myArr.push(this.myArr.splice(0,1)[0]);
   }
  },
};
</script>

