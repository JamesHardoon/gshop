<template>
  <div id="app">
    <router-view/>
    <!-- 只在 首页 搜索 订单 我的 这几个页面才显示底部的Footer组件 -->
    <FooterGuide v-show="$route.meta.showFooter === true"/>
    <!-- <FooterGuide v-show="$route.meta.showFooter"></FooterGuide> -->
  </div>
</template>

<script>
import FooterGuide from './components/FooterGuide/FooterGuide.vue'
import {reqFoodTypes} from './api'
export default {
  name: 'App',
  components: {
    FooterGuide
  },
  data () {
    return {
      
    }
  },
  async mounted () {
    const result = await reqFoodTypes()
    console.log(result)
  }
  
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "./common/stylus/mixins.styl"
  #app
    width 100%
    height 100%
    position relative
</style>
