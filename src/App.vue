<template>
  <div id="app">
    <!-- <img src="~assets/img/detail/cart.png" alt=""> -->
    <router-view />
    <main-tab-bar/>
  </div>
</template>

<script>
  import MainTabBar from 'components/content/mainTabbar/MainTabBar'
export default {
  name: 'App',
  components:{
    MainTabBar
  }
}
</script>

<style lang="less">
@import "@/assets/css/base.css";
</style>
