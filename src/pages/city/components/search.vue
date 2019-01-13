<template>
    <div class="search">
      <input type="text" placeholder="请输入您要搜索的地址" class="text-address">
    </div>
</template>

<script>
export default {
    name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
.search
    background: $bgColor
    height: .72rem
    padding:0 .1rem
    .text-address
        width : 100%
        height: .62rem
        line-height: .62rem
        text-align: center
        border-radius: .1rem
        box-sizing:border-box
        padding: 0 .1rem
        
</style>
