<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommends" :key="item.id">
                <img class="item-img" :src="item.url" >        
                <div class="item-info">
                    <p class="item-title">{{ item.title}}</p>
                    <p class="item-desc">{{ item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    data() {
        return {
            recommends:[
                {
                    id: '0001',
                    url: 'http://img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0002',
                    url: 'http://img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0003',
                    url: 'http://img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
                    title: '临安湍口众安氡温泉',
                    desc: '夏凉冬温，隆冬暖薰蒸，垒垒上浮'
                },{
                    id: '0004',
                    url: 'http://img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
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
.item
    display flex 
    height: 1.9rem
    .item-img
        width: 1.7rem
        height: 1.7rem
        padding : .1rem
    .item-info
        display 1
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
        .item-button
            margin-top: .16rem
            background: #ff9300
            padding: 0 .2rem
            border-radius: .06rem
            color: #fff
            line-height: .44rem
    
</style>

