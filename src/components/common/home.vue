<template>
  <el-container>
    <el-container>
      <el-header><navMenu></navMenu></el-header>
      <el-main><router-view></router-view></el-main>
    </el-container>
  </el-container>
</template>

<script>
import navMenu from './navMenu.vue'

export default {
  components: {
    navMenu
  }
}
</script>

<style>
</style>
