<template>
  <div id="app">  
    <el-container>
      <el-header class="account-header"><Header></Header></el-header>

      <el-container class="account-conter">
        <el-aside class="conter-aside"><Menu></Menu></el-aside>
        <el-main class="conter-main"><router-view></router-view></el-main>
      </el-container>

      <el-footer class="account-footer"><Footer></Footer></el-footer>
    </el-container>
  </div>



</template>

<script>
import Header from './components/layout/Header.vue'
import Footer from './components/layout/Footer.vue'
import Menu from './components/layout/Menu.vue'

export default {
  name: 'App',

  methods:{
    show(){
    alert(123);
    }
  },
  components:{
    Header,Footer,Menu
  }

}
</script>

<style>
    .account-header{
        height: 50px;
        z-index: 9;
        background-color: aqua;
    }
    /* .account-conter{
        
    } */
    .conter-aside{
        width: 230px;
        /* height: 100%; */
        height: auto;
        background-color: bisque;

    }
    .conter-main{
        height: 100%;
        background-color: brown;
    }
    .account-footer{
        position: absolute;
        bottom: 0;
        width: 100%;
        background-color: chartreuse;
    }
</style>
