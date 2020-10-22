<template>
  <el-container class="main-container">
    <el-header>
      <div class="left-box">
        <img src="../assets/img/logo.png">
        <span>管理系统</span>
      </div>
      <div class="right-box">
        <el-dropdown>
          <img src="../assets/img/logo.png">
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item icon="el-icon-house">主页</el-dropdown-item>
            <el-dropdown-item icon="el-icon-ship">讨论</el-dropdown-item>
            <el-dropdown-item icon="el-icon-switch-button">注销</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </div>
    </el-header>
    <el-container>
      <el-aside :width="isCollapse?'60px':'200px'">
        <div class="toggle-box" @click="toggleCollapse">|||</div>
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
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>用户管理</span>
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
  export default {
    name: 'Main',
    data () {
      return {
        isCollapse: true
      }
    },
    methods: {
      toggleCollapse () {
        this.isCollapse = !this.isCollapse
      }
    }
  }
</script>

<style lang="less" scoped>
  .main-container {
    height: 100%;
  }

  .el-header {
    background-color: #001529;
    display: flex;
    justify-content: space-between;
    color: #ffffff;
    padding-left: 0;
    align-items: center;
    font-size: 20px;

    .left-box {
      display: flex;
      align-items: center;

      img {
        width: 60px;
        height: 60px;
        margin: 0 0 10px 15px;
      }

      span {
        margin-left: 15px;
      }
    }

    .right-box {
      .el-dropdown > img {
        height: 60px;
        width: 60px;
        border-radius: 50%;
        background-color: #ffffff;
        margin: 0 15px 0 0;
        background-size: contain;
      }
    }
  }


  .el-aside {
    background-color: #001529;
    color: #333;

    .el-menu {
      border-right: none;
    }

    .toggle-box {
      background-color: chartreuse;
      font-size: 15px;
      font-weight: bolder;
      line-height: 25px;
      color: #ffffff;
      letter-spacing: 0.2em;
      text-align: center;
      cursor: pointer;
    }
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }

  body > .el-container {
    margin-bottom: 40px;
  }

  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }

  .el-icon-arrow-down {
    font-size: 12px;
  }

  .demonstration {
    display: block;
    color: #8492a6;
    font-size: 14px;
    margin-bottom: 20px;
  }
</style>
