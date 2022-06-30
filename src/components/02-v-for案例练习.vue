<template>
  <div>
    <ul>
      <li v-for='(item,index) in navs' :key='item' v-bind:class='{active:index==isShow}' @click='clickFn(index)'>{{item}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navs: ['大学起点', '高中起点', '初中起点', '小学起点'],
      isShow:0,
    };
  },
  methods:{
    clickFn(ind){
      this.isShow=ind;
    }
  }
};
</script>

<style>
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
