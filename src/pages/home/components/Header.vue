<template>
  <div class="header">
    <div class="header-left iconfont">&#xe624;</div>
    <div class="header-input">
      <span class="iconfont searchicon">&#xe632;</span>
      输入城市/经典/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right iconfont">{{ this.city }}&#xe614;</div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
  
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header
    height : $headerHeight
    background : $bgColor
    line-height : $headerHeight
    color : #fff
    width : 100%
    display flex
    .header-left
      float left
      font-size : .36rem
    .header-input
      flex : 1
      background : #fff
      color : #e4e7ea
      border-radius :.06rem
      height : .6rem
      line-height : .6rem
      margin : .14rem 0
      .searchicon
        padding-left : .2rem
    .header-right
      float right
  .header-left
  .header-right
     color : #fff
     display inline-block
     padding: 0 .2rem  
</style>