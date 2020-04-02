<template>
  <div class="nva-home">
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      active-text-color="#ffd04b"
      @select="handleSelect"
    >
      <el-menu-item index="1">
        <div class="head-logo">
          <h2 class="head-title">程心程异少儿编程俱乐部</h2>
          <img v-if="logo" :src="logo" class="sidebar-logo">
        </div>
      </el-menu-item>
      <el-menu-item index="2">首页</el-menu-item>
      <el-menu-item index="3">课程体系</el-menu-item>
      <el-menu-item index="4">师资团队</el-menu-item>
      <el-menu-item index="5">意向加盟</el-menu-item>
      <el-menu-item index="6">最新动态</el-menu-item>
      <el-menu-item index="7">关于我们</el-menu-item>
    </el-menu>
    <div v-if="activeIndex==2">
      <p>首页 </p>
    </div>
    <div v-else-if="activeIndex==3">
      课程体系
    </div>
    <div v-else-if="activeIndex==4">
      师资团队
    </div>
    <div v-else-if="activeIndex==5">
      意向加盟
    </div>
    <div v-else-if="activeIndex==6">
      最新动态
    </div>
    <div v-else-if="activeIndex==7">
      关于我们
    </div>
  </div>
</template>

<script>
import Logo from '@/assets/images/logo.png'
export default {
  data() {
    return {
      title: '程心程异-主页',
      logo: Logo,
      activeIndex: '2'

    }
  },
  methods: {
    handleSelect(key, keyPath) {
      this.activeIndex = key
      console.log(key, keyPath)
    }
  }
}
</script>

<style lang="scss" scoped>
.head-logo {
  width: 50%;

}

.sidebar-logo {
      width: 32px;
      height: 32px;
      vertical-align: middle;
      // left: 240px;

}
.head-logo{
    margin-right: 240px;
      margin-left: 240px;
}

</style>
