<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item  border-bottom" v-for="item of recommends" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.url" >        
                </div>
                <div class="item-info">
                    <p class="item-title">{{ item.title}}</p>
                    <p class="item-desc">{{ item.desc}}</p>
                    <!-- <button class="item-button">查看详情</button> -->
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    data() {
        return {
            recommends:[
                {
                    id: '0001',
                    url: 'http://img1.qunarzz.com/sight/source/1510/c1/afe3ab32b3bc23.jpg_r_640x214_beb61760.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0002',
                    url: 'http://img1.qunarzz.com/sight/source/1510/c1/afe3ab32b3bc23.jpg_r_640x214_beb61760.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0003',
                    url: 'http://img1.qunarzz.com/sight/source/1510/c1/afe3ab32b3bc23.jpg_r_640x214_beb61760.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0004',
                    url: 'http://img1.qunarzz.com/sight/source/1510/c1/afe3ab32b3bc23.jpg_r_640x214_beb61760.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                }
                
            ]
        }
    }

    
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
    height : .8rem
    line-height : .8rem
    background: #eee
    text-indent: .2rem
    margin-top: .2rem
.item-img-wrapper
    height: 0
    width: 100%
    overflow hidden
    padding-bottom: 32.9%
    .item-img
        width: 100%
.item-info
    padding: .1rem
    min-width: 0
    .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
    .item-desc
        line-height : .4rem
        color: #ccc
        ellipsis()
</style>

