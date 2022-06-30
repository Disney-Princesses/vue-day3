<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model="stuName" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model="stuAge" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="stuSex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addeditFn()">添加/修改</button>
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
        <tr v-for="(item, index) in studentInfo" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="stuEdit(index)">编辑</button>
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
      studentInfo: [
        {
          name: "Tom",
          age: 19,
          sex: "男",
        },
        {
          name: "Jone",
          age: 21,
          sex: "女",
        },
      ],
      stuName: "",
      stuAge: 0,
      stuSex: "",
      flag: 1,
      stuIndex: 0,
    };
  },
  methods: {
    addeditFn() {
      if (this.flag) {
        if (this.stuName == "" || this.stuAge == 0 || this.stuSex == "")
          return alert("Please enter");
        this.studentInfo.push({
          name: this.stuName,
          age: this.stuAge,
          sex: this.stuSex,
        });
        this.stuName = "";
        this.stuAge = 0;
        this.stuSex = "";
      } else {
        // this.studentInfo[this.stuIndex] = {
        //   name: this.stuName,
        //   age: this.stuAge,
        //   sex: this.stuSex,
        // } 该赋值vue不能响应式
        this.$set(this.studentInfo[this.stuIndex], 'name', this.stuName)
        this.$set(this.studentInfo[this.stuIndex], 'age', this.stuAge)
        this.$set(this.studentInfo[this.stuIndex], 'sex', this.stuSex)
        // console.log(this.studentInfo);
        this.stuName = "";
        this.stuAge = 0;
        this.stuSex = "";
        this.flag = 1
      }
    },
    stuEdit(index) {
      this.stuName = this.studentInfo[index].name;
      this.stuAge = this.studentInfo[index].age;
      this.stuSex = this.studentInfo[index].sex;
      this.stuIndex = index
      this.flag = 0;
    },
    delFn(index) {
      this.studentInfo.splice(index, 1)
    }
  },
};
</script>

<style></style>
