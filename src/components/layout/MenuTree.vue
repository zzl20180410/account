<template>
  <div>
    <template v-for="value in this.menuData">
        <el-submenu :index="value.index"  v-if="value.node">
            <template slot="title">
                <i :class="value.icon"></i>
                <span slot="title">{{value.menu_name}}</span>
            </template>
            <MenuTree :menuData="value.node"></MenuTree>
        </el-submenu>
        <el-menu-item  :index="value.index" v-else>
            <i :class="value.icon"></i>
            <span slot="title">{{value.menu_name}}</span>
        </el-menu-item>
    </template>
  </div>
</template>

<script>
export default {
  props: ["menuData"],
  name: "MenuTree"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
