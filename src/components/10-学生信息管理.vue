<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model.trim="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addFn">添加/修改</button>
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
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="edit(index)">编辑</button>
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
      arr: [
        {
          name: "Tom",
          age: 25,
          sex: "女",
        },
        {
          name: "Jone",
          age: 21,
          sex: "女",
        },
      ],
      name: "",
      age: 0,
      sex: "",
      flag: false,
      key: 0,
    };
  },
  methods: {
    addFn() {
      if (this.name == "" || this.age == 0 || this.sex == "")
        return alert("请填写信息后再提交！");
      if (this.flag) {
        this.flag = false;
        this.arr.splice(this.key, 1, {
          name: this.name,
          age: this.age,
          sex: this.sex,
        });
      } else {
        this.arr.push({
          name: this.name,
          age: this.age,
          sex: this.sex,
        });
      }
    },
    delFn(ind) {
      this.arr.splice(ind, 1);
    },
    edit(ind) {
      this.flag = true;
      this.key = ind;
      this.name = this.arr[ind].name;
      this.age = this.arr[ind].age;
      this.sex = this.arr[ind].sex;
    },
  },
};
</script>