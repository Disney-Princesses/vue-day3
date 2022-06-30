<template>
  <div>
    <div v-for="(item, index) in arr" :key="index" style="display:inline-block">
      <input type="checkbox"  @change='changeFn' v-model='isChecked' :value='item'/>
      <span>{{ item }}</span>
    </div>
    <p>你选中的元素, 累加的值和为:{{count}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      isChecked: [],
      count:0,
    };
  },
  methods:{
    changeFn(){
     console.log(this.isChecked);
     this.count=this.isChecked.reduce((sum,val)=>sum+val,0);
    }
  }
};
</script>

<style>
</style>