<template>
  <!-- 1.帅哥美女走一走 -->
  <!-- <div>  
    <ul>
      <li v-for="item in myArr" :key="item">{{ item }}</li>
    </ul>
    <button @click="btn">走一走</button>
  </div> -->
  <!-- 2.加加减减 -->
  <!-- <div id="app">
    <ul>
      <li v-for="(item, ind) in arr" :key="item">
        <span>{{ item }}</span>
        <button @click="del(ind)">删除</button>
      </li>
    </ul>
    <button @click="add">生成</button>
  </div> -->
<!-- 3.购物车 -->
 <div id="app">
    <table class="tb">
      <tr>
        <th>编号</th>
        <th>品牌名称</th>
        <th>创立时间</th>
        <th>操作</th>
      </tr>
      <!-- 循环渲染的元素tr -->
      <tr v-for="(item,index) in list" :key="item.id">
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
            <td>{{item.time}}</td>
            <td>
                <button @click="del(index)">删除</button>
            </td>
        </tr>
      <tr v-if="list.length === 0">
        <td colspan="4">没有数据咯~</td>
      </tr>
    </table>
  </div>
</template>
<script>
//1.帅哥美女走一走
// export default {
//   data() {
//     return {
//       myArr: ["帅哥", "美女", "程序猿"],
//     };
//   },
//   methods: {
//     btn() {
//       // 头部数据加入到末尾
//       this.myArr.push(this.myArr[0]);
//       // 再把头部的数据删除掉
//       this.myArr.shift();
//     },
//   },
// };
//2.加加减减
// export default {
//   data() {
//     return {
//       arr: [1, 5, 3],
//     };
//   },
//   methods: {
//     add() {
//       this.arr.push(Math.floor(Math.random() * 20));
//     },
//     del(index) {
//       this.arr.splice(index, 1);
//     },
//   },
// };
//购物车
export default {
  data() {
    return {
      list: [
        { id: 1, name: "奔驰", time: "2020-08-01" },
        { id: 2, name: "宝马", time: "2020-08-02" },
        { id: 3, name: "奥迪", time: "2020-08-03" },
      ],
    };
  },
  methods: {
    del(index) {
      // 删除按钮 - 得到索引, 删除数组里元素
      this.list.splice(index, 1);
    },
  },
};
</script>

<style scoped>
/* 购物车 */
#app {
  width: 600px;
  margin: 10px auto;
}

.tb {
  border-collapse: collapse;
  width: 100%;
}

.tb th {
  background-color: #0094ff;
  color: white;
}

.tb td,
.tb th {
  padding: 5px;
  border: 1px solid black;
  text-align: center;
}

.add {
  padding: 5px;
  border: 1px solid black;
  margin-bottom: 10px;
}
</style>
