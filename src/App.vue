<template>
  <div id="app">
    <Dheader></Dheader>
    <transition name="fade">
      <keep-alive exclude="moviesDetail"><!-- 缓存组件，避免多次加载 ，提高性能。其中exclude是针对性缓存指定组件的，如果缓存太多也会影响性能-->
        <router-view></router-view>
      </keep-alive>
    </transition>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'hello vue'
    }
  },
  components: {//es6引入组件新方式
    'Dheader': (resolve) => {
      require(['./header'], resolve)
    }
  }
}
</script>

<style lang="less" rel="stylesheet/less">

  *{
    margin: 0;
    padding: 0;
    font-family: '微软雅黑';
  }
</style>
