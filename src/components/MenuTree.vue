<template>
    <div>
      <template v-for="item in this.MenuList">
        <el-menu
          default-active="2"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose"
          background-color="#001529"
          text-color="#fff"
          active-text-color="#ffd04b"
          :collapse="isCollapse"
          :collapse-transition="false">
          <el-submenu :disabled="item.disabled" :index="item.id+''" :key="item.id+''" :v-if="item.children.length()>0">
            <template slot="title">
              <i :class="item.icon"></i>
              <span slot="title">{{item.menuName}}</span>
            </template>
            <menu-tree :menu-list="item.children"></menu-tree>
          </el-submenu>
        </el-menu>
      </template>
    </div>
</template>

<script>
  export default {
    name: 'MenuTree',
    props:["MenuList"]
  }
</script>

<style scoped>

</style>
