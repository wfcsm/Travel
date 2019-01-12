<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                    <img class="icon-img-content" :src="item.url">
                    </div>
                    <p class="icon-desc">{{ item.desc}}</p>
                </div>
            </swiper-slide>
            <!-- <swiper-slide>
                <div class="icon">
                    <div class="icon-img">
                    <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
                    </div>     
                    <p class="icon-desc">景点门票</p>
                </div>
            </swiper-slide> -->
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data () {
        return {
            iconList:  [
                {
                    id: '0001',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },{
                    id: '0002',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0003',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0004',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0005',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0006',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0007',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0008',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0009',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
                {
                    id: '0001',
                    url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    desc: '景点门票'
                },
            ]
        }
    },
    computed: {
       pages (){
         let pages = []
         this.iconList.forEach((a, b)=>{
             let page = Math.floor(b / 8);
             if(!pages[page]){
                 pages[page]=[]
             }
             pages[page].push(a)
         })
         return pages
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 50%
.icon
    position: relative
    float: left
    overflow: hidden
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
            height: 100%
            display block
            margin: 0 auto 
    .icon-desc
        position absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: #333
        ellipsis()

</style>


