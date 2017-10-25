<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1 v-text="msg"></h1>
    <pagination :totalPage="parentTotalPage" :currentPage="parentCurrentpage" :changeCallback="parentCallback"></pagination>
    <!-- <router-view/> -->
  </div>
</template>

<script>
import Pagination from './components/pagination'
export default {
  name: 'app',
  data () {
    return {
      msg : "Update your data here.",
      //在data中初始化总页数totalPage，和当前页currentPage
      parentTotalPage: 10,
      parentCurrentpage: 1
    }
  },
  //使用pagination组件
  components: { Pagination },
  methods:{
    //在这里传入pagination的跳转页码回调方法
    //cPage参数是已跳转的当前页码
    parentCallback( cPage )  {
      //这里是页码变化后要做的事
      this.msg = 'Update your data here. Page: ' + cPage;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
