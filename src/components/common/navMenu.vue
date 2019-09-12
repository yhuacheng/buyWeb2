<template>
  <div class="menubox">
    <el-row class="menu-inbox">
      <el-col :span="4">
        <div class="login-logo">HotBuy</div>
      </el-col>
      <el-col :span="20">
        <el-menu :default-active="onRoutes" class="el-menu-vertical-demo" mode="horizontal" @open="handleOpen" @close="handleClose" router>
          <el-menu-item index="loginHome">
            <i class="el-icon-s-home"></i>
            <span slot="title">首页</span>
          </el-menu-item>
          <el-menu-item index="taskManage">
            <i class="el-icon-s-platform"></i>
            <span slot="title">任务</span>
          </el-menu-item>
          <el-menu-item index="accountManage">
            <i class="el-icon-s-data"></i>
            <span slot="title">收支</span>
          </el-menu-item>
          <el-menu-item index="help">
            <i class="el-icon-question"></i>
            <span slot="title">帮助</span>
          </el-menu-item>
          <el-menu-item index="1" class="login-out" @click="loginOut">
            <i class="el-icon-error"></i>
            <span slot="title">退出</span>
          </el-menu-item>
          <el-submenu index="2" class="login-user">
              <template slot="title"><i class="el-icon-user-solid"></i>刘德华</template>
              <el-menu-item index="userInfo">基本信息</el-menu-item>
              <el-menu-item index="updatePwd">修改密码</el-menu-item>
              <el-menu-item index="securitySet">安全设置</el-menu-item>
          </el-submenu>
        </el-menu>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    name: 'navMenu',
    computed: {
      onRoutes() {
        return this.$route.path.replace('/', '')
      }
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      },
      loginOut() {
        this.$router.push('/index')
        sessionStorage.clear()
      }
    }
  }
</script>

<style>
</style>
