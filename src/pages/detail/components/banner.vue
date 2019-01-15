<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_600x330_82e4e08f.jpg" alt="">
            <div class="banner-info">
                <div class="banner-title">
                    临安湍口众安氡温泉
                </div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe632;</span>39</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary.vue'
export default {
    name: 'DetailBanner',
    data () {
        return {
            showGallary:false,

            imgs:['http://img1.qunarzz.com/sight/p0/201309/25/8467e5a355a15839c8d65eac.jpg_r_800x800_af21b89d.jpg',
            'http://img1.qunarzz.com/sight/p0/1502/69/69abe0f29531fd18.water.jpg_r_800x800_bb19a3e5.jpg']
        }
    },
    methods:{
        handleBannerClick () {
            this.showGallary = true
        },
        handleGallaryClose () {
             this.showGallary = false
        }

    },
    components:{
        CommonGallary
    }
}
</script>

<style lang="stylus" scoped>
.banner
    position relative
    padding-bottom:55%
    height:0
    overflow hidden
    .banner-img
        width:100%
    .banner-info
        display flex
        position absolute
        left:0
        right: 0
        bottom: 0
        line-height: .6rem
        color: #fff
        background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
        .banner-title
            line-height: .4rem
            font-size: .36rem
            padding: 0 .2rem
        .banner-number
            padding:0 .4rem
            line-height: .4rem
            height: .4rem
            border-radius: .2rem
            background: rgba(0,0,0, .8)
            .banner-icon
                
                font-size: .24rem

        

   
</style>
