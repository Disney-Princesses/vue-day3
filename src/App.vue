<template>
  <div id="app">
    <div class="box">
      <div>
        <span>姓名:</span>
        <input type="text" v-model="name" />
      </div>
      <div>
        <span>年龄:</span>
        <input type="number" v-model="age" />
      </div>
      <div>
        <span>性别:</span>
        <select v-model="sex">
          <option value="男">男</option>
          <option value="女">女</option>
        </select>
      </div>
      <div>
        <button @click="addFn">添加/修改</button>
      </div>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="item in arr" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(item.id)">删除</button>

            <button @click="setData(item.id)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arr: [],
      id: "",
      name: "",
      age: 0,
      sex: "",
      temp: false,
    };
  },
  methods: {
    addFn() {
      if (this.name == "" || this.age == "" || this.sex == "") {
        alert("内容不能为空");
      } else {
        const obj = {
          id: "",
          name: this.name,
          age: this.age,
          sex: this.sex,
        };

        if (this.id) {
          obj.id = this.id;
          const index = this.arr.findIndex((ele) => ele.id == this.id);

          this.$set(this.arr, index, obj);
        } else {
          obj.id =
            this.arr.length !== 0 ? this.arr[this.arr.length - 1].id + 1 : 1;
          this.arr.push(obj);
        }

        this.id = "";
        this.name = "";
        this.age = "";
        this.sex = "";
      }
    },
    delFn(val) {
      const index = this.arr.findIndex((ele) => ele.id == val);
      this.arr.splice(index, 1);
    },
    setData(val) {
      const index = this.arr.findIndex((ele) => ele.id == val);
      this.id = val;
      this.name = this.arr[index].name;
      this.age = this.arr[index].age;
      this.sex = this.arr[index].sex;
    },
  },
};
</script>
<style>
table tr th,
table tr td {
  width: 150px;
  height: 67px;
  border: 1px solid black;
  border-collapse: collapse;
}
table {
  margin: 50px 0 0 50px;
}
button {
  float: left;
  margin: 0, 10px;
}
.box {
  margin: 50px 0 0 50px;
}
</style>
