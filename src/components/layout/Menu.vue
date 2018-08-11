<template>
 <div :class="saidAotuClass">
    <div style="height:30px;text-align: right;"><li :class="this.saidButoon" @click="saidAotu"></li></div>
    <el-menu class="menu-Bar" :collapse="isCollapse"
    background-color="#242424"
    text-color="#B23AEE"
    active-text-color="#CD0000"
    :router="true"
     default-active="1" >
        <MenuTree :menuData="this.menuData"></MenuTree>
    </el-menu>
  </div>
</template>

<script>
import MenuTree from "./MenuTree";
export default {
  name: "Menu",
  data() {
    return {
      isCollapse: false,
      saidButoon:"el-icon-arrow-left",
      saidAotuClass:"said-aotu-1",
      menuData: []
    };
  },
  created(){
    //this.getMenu()
  },
  mounted(){
    this.getMenu()
  },
  methods: {
    getMenu() {
        this.menuData = [
        {
          id: 1,
          index:"1",
          parent_id: 0,
          menu_name: "第一级菜单 1",
          sorting: 0,
          icon:"el-icon-message",
          node: [
              {
              id: 2,
              index:"/",
              parent_id: 1,
              menu_name: "第二级菜单 1-1",
              sorting: 0,
              icon:"el-icon-message",
            }

          ]
        },
        {
          id: 4,
          index:"2",
          parent_id: 0,
          menu_name: "第一级菜单 2",
          sorting: 0,
          icon:"el-icon-phone",
          node: [
            {
              id: 5,
              index:"/d",
              parent_id: 4,
              menu_name: "第二级菜单 2-1",
              sorting: 0,
              icon:"el-icon-service",
            }
          ]
        }
      ]
    },
    saidAotu(){
      this.isCollapse = !this.isCollapse;
      if(this.isCollapse){
        this.saidButoon = "el-icon-arrow-right";
        this.saidAotuClass = "said-aotu-2";
      }else{
        this.saidAotuClass = "said-aotu-1";
        this.saidButoon = "el-icon-arrow-left";
      }    
    }
  },
  components: {
    "MenuTree": MenuTree,
    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .said-aotu-1{
    
  }
  .said-aotu-2{
    
    width: 80px;
  }
   /* .menu-Bar:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  } */
</style>
