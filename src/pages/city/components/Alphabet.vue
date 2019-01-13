<template>
    <ul class="list" >
        <li class="item" v-for="(item, key) of alpabet" :key="key">
            {{ key }}
        </li>  
    </ul>
</template>

<script>
export default {
   name: 'CityAlphabet',
   props: {
      alpabet:Object
   }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
    .list
        position absolute
        top: 1.58rem
        right: 0
        bottom: 0
        width: .4rem
        display: flex
        flex-direction:column
        justify-content center
        .item
           line-height: .44rem
           text-align: center
           color: $bgColor 
       
</style>
