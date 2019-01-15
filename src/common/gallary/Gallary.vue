<template>
    <div class="container" @click="handleGallaryClick">
        <div class="wrapper">
            <swiper :options="swiperOptions" >
                <!-- slides -->
                <swiper-slide v-for="(item, index) in imgs" :key="index">
                    <img class="gallary-img" :src="item">
                </swiper-slide>
                <!-- Optional controls -->
                <div class="swiper-pagination" slot="pagination" ></div>
            </swiper>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CommonGallay',
    props:{
        imgs: {
            type:Array,
            default (){
                return ['//img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_600x330_82e4e08f.jpg','http://img1.qunarzz.com/sight/p0/201309/25/8467e5a355a15839c8d65eac.jpg_r_800x800_af21b89d.jpg']
            }
        }
    },
    data () {
        return {
            swiperOptions:{
                pagination: '.swiper-pagination',
                paginationType: 'fraction',
                observeParents:true,
                observer: true
            }
        }
    },
    methods:{
        handleGallaryClick (){
            this.$emit('close')
        }
    }
}
</script>

<style lang="stylus" scoped>
    .container >>> .swiper-container
        overflow: inherit
    .container
        z-index: 99
        position: fixed
        left: 0
        right: 0
        top: 0
        bottom: 0
        background:#000
        display flex
        flex-direction: column
        justify-content: center
        .wrapper
            overflow hidden
            height:0
            width:100%
            padding-bottom: 100%
            .gallary-img
                width:100%
            .swiper-pagination
                color: #fff
                bottom:-1rem
</style>
