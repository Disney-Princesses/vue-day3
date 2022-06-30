<template>
  <div id="app">
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
      <select v-model="gender">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addOrChange">添加/修改</button>
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
        <tr v-for="(item, index) in arr" :key="item">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="editFn(index)">编辑</button>
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
          name: '张三',
          age: 19,
          sex: '男',
        },
        {
          name: '李四',
          age: 29,
          sex: '男',
        },
        {
          name: '赵青',
          age: 16,
          sex: '女',
        },
      ],
      name: '',
      age: '',
      gender: '男',
      flag: false
    }
  },
  methods: {
    addOrChange(index) {
      // if (flag) {
      //   this.arr[index].name = this.name
      //   this.arr[index].age = this.age
      //   this.arr[index].sex = this.gender
      //   this.flag = false
      // }
      if (this.name.trim() === '') {
        return alert('请输入内容')
      }
      this.arr.push({
        name: this.name,
        age: this.age,
        sex: this.gender
      })
    },
    delFn(index) {
      this.arr.splice(index, 1)
    },
    editFn(index) {
      this.flag = true
      this.name = this.arr[index].name
      this.age = this.arr[index].age
      this.sex = this.arr[index].gender

      // this.arr[index]={
      //   name:this.name,
      //   age:this.age,
      //   gender:this.gender
      // }
    }
  }

}
</script>
