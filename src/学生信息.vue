<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="uname" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="uage" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="usex">
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
        <tr v-for="(item, index) in arr" :key="item.name">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="editorFn(item, index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  name: "app",
  data() {
    return {
      arr: [
        {
          name: "zs",
          age: 17,
          sex: "男",
        },
        {
          name: "ls",
          age: 13,
          sex: "女",
        },
        {
          name: "ww",
          age: 20,
          sex: "女",
        },
        {
          name: "zl",
          age: 39,
          sex: "男",
        },
      ],
      uname: "",
      uage: "",
      usex: "",
      indexQ: 0,
      flag: 1,
    };
  },
  methods: {
    addFn() {
      if (this.flag) {
        if (this.uname == "" || this.uage == "" || this.usex == "") {
          alert("请输入内容");
        }
        // 新增数据
        this.arr.push({
          name: this.uname,
          age: this.uage,
          sex: this.usex,
        });
        (this.uname = ""), (this.uage = ""), (this.uage = "");
      } else {
        // 修改数据
        this.$set(this.arr[this.indexQ], "name", this.uname);
        this.$set(this.arr[this.indexQ], "age", this.uage);
        this.$set(this.arr[this.indexQ], "sex", this.usex);
         (this.uname = ""), (this.uage = ""), (this.uage = "");
         this.flag=1
      }
    },
    delFn(index) {
      this.arr.splice(index, 1);
    },
    editorFn(item, index) {
      this.uname = item.name;
      this.uage = item.age;
      this.usex = item.sex == "男" ? "男" : "女";
      this.indexQ = index;
      this.flag = 0;
    },
  },
};
</script>
