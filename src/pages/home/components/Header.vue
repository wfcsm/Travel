<template>
  <div class="header">
    <a class="header-left iconfont">&#xe624;</a>
    <div class="header-input">
      <span class="iconfont searchicon">&#xe632;</span>
      输入城市/经典/游玩主题
    </div>
    <a class="header-right iconfont">杭州&#xe614;</a>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header
    height : .88rem
    background : $bgColor
    line-height : .88rem
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