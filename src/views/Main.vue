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
        <menu-tree :MenuList="this.MenuList"></menu-tree>
      </el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
  import MenuTree from '../components/MenuTree'

  export default {
    name: 'Main',
    components: { MenuTree },
    data () {
      return {
        isCollapse: true,
        MenuList:[
          {
            "id": 1,
            "parentId": 0,
            "menuName": "系统管理",
            "url": "",
            "icon": "el-icon-setting",
            "orderNum": 1,
            "open": 1,
            "disabled": false,
            "perms": null,
            "type": 0,
            "children": [
              {
                "id": 253,
                "parentId": 1,
                "menuName": "欢迎页面",
                "url": "/welcome",
                "icon": "el-icon-star-off",
                "orderNum": 1,
                "open": 0,
                "disabled": false,
                "perms": "welcome:view",
                "type": 0,
                "children": []
              },
              {
                "id": 226,
                "parentId": 1,
                "menuName": "用户管理",
                "url": "/users",
                "icon": "el-icon-user",
                "orderNum": 2,
                "open": 0,
                "disabled": false,
                "perms": "users",
                "type": 0,
                "children": []
              },
              {
                "id": 321,
                "parentId": 1,
                "menuName": "附件管理",
                "url": "/attachments",
                "icon": "el-icon-picture-outline",
                "orderNum": 2,
                "open": 1,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              },
              {
                "id": 4,
                "parentId": 1,
                "menuName": "菜单权限",
                "url": "/menus",
                "icon": "el-icon-help",
                "orderNum": 3,
                "open": 0,
                "disabled": false,
                "perms": null,
                "type": 0,
                "children": []
              },
              {
                "id": 235,
                "parentId": 1,
                "menuName": "角色管理",
                "url": "/roles",
                "icon": "el-icon-postcard",
                "orderNum": 3,
                "open": 0,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              },
              {
                "id": 261,
                "parentId": 1,
                "menuName": "部门管理",
                "url": "/departments",
                "icon": "el-icon-s-home",
                "orderNum": 3,
                "open": 0,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              },
              {
                "id": 319,
                "parentId": 1,
                "menuName": "公告管理",
                "url": "/notices",
                "icon": "el-icon-s-flag",
                "orderNum": 4,
                "open": 0,
                "disabled": true,
                "perms": "",
                "type": 0,
                "children": []
              }
            ]
          },
          {
            "id": 312,
            "parentId": 0,
            "menuName": "业务管理",
            "url": null,
            "icon": "el-icon-s-goods",
            "orderNum": 2,
            "open": 0,
            "disabled": false,
            "perms": null,
            "type": 0,
            "children": [
              {
                "id": 229,
                "parentId": 312,
                "menuName": "物资管理",
                "url": "",
                "icon": "el-icon-date",
                "orderNum": 1,
                "open": 1,
                "disabled": false,
                "perms": "el-icon-date",
                "type": 0,
                "children": [
                  {
                    "id": 230,
                    "parentId": 229,
                    "menuName": "物资入库",
                    "url": "/inStocks",
                    "icon": "el-icon-date",
                    "orderNum": 1,
                    "open": 1,
                    "disabled": false,
                    "perms": "el-icon-date",
                    "type": 0,
                    "children": []
                  },
                  {
                    "id": 267,
                    "parentId": 229,
                    "menuName": "物资资料",
                    "url": "/products",
                    "icon": "el-icon-goods",
                    "orderNum": 2,
                    "open": 0,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  },
                  {
                    "id": 268,
                    "parentId": 229,
                    "menuName": "物资类别",
                    "url": "/productCategorys",
                    "icon": "el-icon-star-off",
                    "orderNum": 2,
                    "open": 0,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  },
                  {
                    "id": 270,
                    "parentId": 229,
                    "menuName": "物资发放",
                    "url": "/outStocks",
                    "icon": "el-icon-goods",
                    "orderNum": 5,
                    "open": 1,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  },
                  {
                    "id": 316,
                    "parentId": 229,
                    "menuName": "物资库存",
                    "url": "/stocks",
                    "icon": "el-icon-tickets",
                    "orderNum": 5,
                    "open": 0,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  }
                ]
              },
              {
                "id": 311,
                "parentId": 312,
                "menuName": "物资流向",
                "url": null,
                "icon": "el-icon-edit",
                "orderNum": 3,
                "open": 0,
                "disabled": false,
                "perms": null,
                "type": 0,
                "children": [
                  {
                    "id": 310,
                    "parentId": 311,
                    "menuName": "物资去处",
                    "url": "/consumers",
                    "icon": "el-icon-edit",
                    "orderNum": 1,
                    "open": 0,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  },
                  {
                    "id": 269,
                    "parentId": 311,
                    "menuName": "物资来源",
                    "url": "/suppliers",
                    "icon": "el-icon-coordinate",
                    "orderNum": 5,
                    "open": 0,
                    "disabled": false,
                    "perms": "",
                    "type": 0,
                    "children": []
                  }
                ]
              }
            ]
          },
          {
            "id": 303,
            "parentId": 0,
            "menuName": "健康报备",
            "url": "",
            "icon": "el-icon-platform-eleme",
            "orderNum": 3,
            "open": 0,
            "disabled": false,
            "perms": "",
            "type": 0,
            "children": [
              {
                "id": 273,
                "parentId": 303,
                "menuName": "全国疫情",
                "url": "/map",
                "icon": "el-icon-s-opportunity",
                "orderNum": 1,
                "open": 1,
                "disabled": false,
                "perms": "map:view",
                "type": 0,
                "children": []
              },
              {
                "id": 304,
                "parentId": 303,
                "menuName": "健康打卡",
                "url": "/health",
                "icon": "el-icon-s-cooperation",
                "orderNum": 1,
                "open": 0,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              },
              {
                "id": 305,
                "parentId": 303,
                "menuName": "查看情况",
                "url": null,
                "icon": "el-icon-c-scale-to-original",
                "orderNum": 2,
                "open": 1,
                "disabled": false,
                "perms": null,
                "type": 0,
                "children": []
              },
              {
                "id": 272,
                "parentId": 303,
                "menuName": "疫情辟谣",
                "url": "/rumors",
                "icon": "el-icon-help",
                "orderNum": 5,
                "open": 0,
                "disabled": false,
                "perms": null,
                "type": 0,
                "children": []
              }
            ]
          },
          {
            "id": 295,
            "parentId": 0,
            "menuName": "其他管理",
            "url": "",
            "icon": "el-icon-s-marketing",
            "orderNum": 5,
            "open": 0,
            "disabled": false,
            "perms": "",
            "type": 0,
            "children": [
              {
                "id": 297,
                "parentId": 295,
                "menuName": "监控管理",
                "url": "",
                "icon": "el-icon-warning",
                "orderNum": 1,
                "open": 0,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": [
                  {
                    "id": 298,
                    "parentId": 297,
                    "menuName": "SQL监控",
                    "url": "/druid",
                    "icon": "el-icon-view",
                    "orderNum": 1,
                    "open": 0,
                    "disabled": false,
                    "perms": null,
                    "type": 0,
                    "children": []
                  }
                ]
              },
              {
                "id": 341,
                "parentId": 295,
                "menuName": "个人博客",
                "url": "/blog",
                "icon": "el-icon-view",
                "orderNum": 1,
                "open": 0,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              },
              {
                "id": 296,
                "parentId": 295,
                "menuName": "swagger文档",
                "url": "/swagger",
                "icon": "el-icon-document",
                "orderNum": 2,
                "open": 0,
                "disabled": false,
                "perms": null,
                "type": 0,
                "children": []
              },
              {
                "id": 318,
                "parentId": 295,
                "menuName": "图标管理",
                "url": "/icons",
                "icon": "el-icon-star-off",
                "orderNum": 2,
                "open": 1,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              }
            ]
          },
          {
            "id": 5,
            "parentId": 0,
            "menuName": "日志管理",
            "url": "/logs",
            "icon": "el-icon-camera",
            "orderNum": 6,
            "open": 0,
            "disabled": false,
            "perms": null,
            "type": 0,
            "children": [
              {
                "id": 271,
                "parentId": 5,
                "menuName": "登入日志",
                "url": "/loginLog",
                "icon": "el-icon-date",
                "orderNum": 1,
                "open": 0,
                "disabled": false,
                "perms": "login:log",
                "type": 0,
                "children": []
              },
              {
                "id": 307,
                "parentId": 5,
                "menuName": "操作日志",
                "url": "/logs",
                "icon": "el-icon-edit",
                "orderNum": 1,
                "open": 1,
                "disabled": false,
                "perms": "",
                "type": 0,
                "children": []
              }
            ]
          }
        ]
      }
    },
    comments: {
      MenuTree
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
