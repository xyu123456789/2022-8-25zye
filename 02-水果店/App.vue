<template>
  <div>
    <span>欢迎光临_vue开发的收银系统_水果店</span>
    <ul>
      <li><strong>苹果10￥/斤,折扣8折</strong></li>
      <li>
        请你输入你要购买的斤数<input type="text" value="0" v-model="Price" />
      </li>
      <li><button @click.prevent="add">结账买单~</button></li>
      <li>
        结账单:&nbsp;总价:&nbsp;{{ zj }}￥元折后价:&nbsp;{{ zhj }}￥元省了{{
          sq
        }}￥元
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      Price: 0,
      zj: 0,
      zhj: 0,
      sq: 0,
    };
  },
  methods: {
    add() {
      this.zj = this.Price * 10;
      this.zhj = this.zj * 0.8;
      this.sq = this.zj - this.zhj;
    },
  },
};
</script>

<style scope>
div {
  width: 700px;
  height: 120px;
  margin: 0 auto;
  text-align: center;
}
ul {
  list-style: none;
  margin: 0px;
  padding: 0px;
}
ul li {
  border: 1px solid #666;
  text-align: center;
  margin-top: 2px;
}
</style>