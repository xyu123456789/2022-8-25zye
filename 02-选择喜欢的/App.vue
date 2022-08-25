<template>
  <div>
    <hr />
    <span>请你选择你喜欢的专栏</span>
    <ul>
      <li v-for="(item, index) in Loved" :key="index">
        <span> {{ item }}</span>
        <input type="checkbox" v-model="check" :value="item"/>
      </li>
    </ul>
    <span v-for="(item, index) in check" :key="index">{{item}}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      Loved: ["科幻", "喜剧", "动漫", "冒险", "科技", "军事", "娱乐", "奇闻"],
      check: [],
    };
  },
  methods: {
  
  },
};
</script>

<style scope>
ul {
  list-style: none;
  display: flex;
}
</style>