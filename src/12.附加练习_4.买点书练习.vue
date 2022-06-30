<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="(item, index) in arr" :key="item">
        <span>{{ item.name }}</span>
        <button @click="addBook(index)">买书</button>
      </li>
    </ul>
    <table border="1" width="500" cellspacing="0">
      <tr v-for="item in arr" :key="item.id">
        <th>{{ item.id }}</th>
        <th>{{ item.name }}</th>
        <th>{{ item.price }}</th>
        <th>{{ item.count }}</th>
        <th>{{ item.price * item.count }}</th>
      </tr>
    </table>
    <p>总价格为:{{ getSum }} </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          id: 1,
          name: "水浒传",
          price: 107,
          count: 0,
        },
        {
          id: 2,
          name: "西游记",
          price: 192,
          count: 0,
        },
        {
          id: 3,
          name: "三国演义",
          price: 219,
          count: 0,
        },
        {
          id: 4,
          name: "红楼梦",
          price: 178,
          count: 0,
        },
      ],
    };
  },
  methods: {
    addBook(index) {
      this.arr[index].count++
    }
  },
  computed:{
    getSum() {
     return this.arr.reduce((sum, obj) => sum += obj.price*obj.count, 0)
    }
  }
};
</script>