<!--首页的list-->
<template>
  <div class="pageList">
    <router-link :to="'details?pid='+data.pid+'&title='+data.title">
      <p class="pageList-title">{{data.title}}</p>
      <p v-for="(item ,index) in JSON.parse(data.content)">{{item}}</p>
    </router-link>
    <ul class="pageList-ul" v-if="data.img">
      <li class="pageList-ul-li" v-for="item in JSON.parse(data.img)">
        <a
          :href="item"><img
          :src="item"></a>
      </li>
    </ul>
    <p>创建人：{{data.creater}}  回复({{data.num}})</p>
  </div>
</template>
<script>
  export default({
    name: 'pageList',
    data(){
      return {
        content: ""
      }
    },
    props: ["data"],
    components: {}
  })
</script>
<style scoped>
  .pageList {
    background: #fafafa;
    border-bottom: 1px solid darkcyan;
    border-top: 0;
  }

  .pageList a {
    color: #333;
  }

  .pageList-title {
    height: 30px;
    width: 100%;
    overflow: hidden;
    line-height: 30px;
    font-size: 16px;
    border-bottom: 1px solid #ddd;
  }

  .pageList-ul {
    width: 90%;
    padding: 5%;
  }

  .pageList-ul {

  }

  .pageList-ul-li {
    display: inline-block;
    min-width: 30%;
    width: 30%;
    padding-left: 2%;
  }

  .pageList-ul-li img {
    width: 100%;
  }
</style>
