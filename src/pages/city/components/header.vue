<template>
    <div class="header">
        <router-link to="/">
            <div class="header-back iconfont">&#xe624;</div>
        </router-link>
        城市选择
        
    </div>
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
.header
    position relative
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    overflow hidden
    color: #fff
    background: $bgColor
    font-size: .32rem
    .header-back
        width: .64rem
        position absolute
        top: 0
        left: 0
        color : #fff
        padding: 0 .2rem  
        font-size: .4rem
</style>
