<template>
    <div>
        <div class="search">
            <input v-model="keyword" type="text" placeholder="请输入您要搜索的地址" class="text-address">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item of list" :key="item.id" >{{ item.name }}</li>
                <li class="search-item border-bottom" v-show="hasList">没有找到匹配城市</li>
            </ul>
        </div>
    </div>
    
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name: 'CitySearch',
    props: {
        cities: Object
    },
    computed:{
        hasNoData(){
            return !this.list.length
        }
    },
    data(){
        return {
            keyword: '',
            list: [],
            timer: null

        }
    },
    watch: {
        keyword () {
            if (this.timer){
                clearTimeout(this.timer)
            }
            if (!this.keyword){
                this.list = []
                return
            }
            this.timer = setTimeout(()=> {
                let result = []
                for(let i in this.cities){
                    this.cities[i].forEach((value)=>{
                        if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) >-1){
                            result.push(value)
                        }
                    })
                }
                this.list=result
            },100)
        }
    },
    mounted () {
        this.scroll = new BScroll(this.$refs.search)
    }
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
.search-content   
    z-index :1
    overflow hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
        line-height: .76rem
        color: #666
        padding-left: .2rem    
        background: #fff
</style>
