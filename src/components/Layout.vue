<template>
  <el-container>
    <el-menu
        default-active="1-4-1"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        :collapse="isCollapse"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b">
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span slot="title">导航一</span>
          </template>
          <el-menu-item-group>
            <span slot="title">分组一</span>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="1-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="1-4">
            <span slot="title">选项4</span>
            <el-menu-item index="1-4-1">选项1</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">导航二</span>
        </el-menu-item>
        <el-menu-item index="3">
          <i class="el-icon-setting"></i>
          <span slot="title">导航三</span>
        </el-menu-item>
      </el-menu>
    <el-container>
      <el-header>
        <div class="toggle-container" @click="handleToggle"><i class="icon icon-option icon-toggle"></i></div>
      </el-header>
      <el-main>
        <div class="body-content">
          <router-view></router-view>
        </div>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
    export default {
      name: 'layout',
      data () {
        return {
          isCollapse: false,
          asideWidth: '280px'
        }
      },
      methods: {
        handleOpen (key, keyPath) {
          console.log(key, keyPath)
        },
        handleClose (key, keyPath) {
          console.log(key, keyPath)
        },
        handleToggle () {
          this.isCollapse = !this.isCollapse
          if (this.isCollapse) {
            this.asideWidth = '65px'
          } else {
            this.asideWidth = '260px'
          }
        }
      }
    }
</script>

<style scoped>
  .el-container {
    height: 100%;
  }
  .el-aside {
    width: 280px;
  }
  .el-header {
    padding: 0;
  }
  .el-menu-vertical-demo {
    height: 100%;
    width: 65px;
  }
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 260px;
  }
  .toggle-container {
    height: 60px;
    position: relative;
    z-index: 1;
    width: 42px;
    line-height: 60px;
    background-color: #FBFBFB;
    text-align: center;
    cursor: pointer;
  }
</style>
