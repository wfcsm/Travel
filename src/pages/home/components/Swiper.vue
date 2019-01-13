<template>
  <div class="wrap">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination" ></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: '.swiper-pagination',
        autoplay : 2000,  //自动切换的时间间隔（单位ms），不设定该参数slide不会自动切换
        autoplayDisableOnInteraction: false, //用户操作swiper之后，是否禁止autoplay。默认为true：停止。
        paginationClickable:true
      }
    }
    
  },
  computed: {
    showSwiper(){
      return this.list.length
    }
  }
};
</script>

<style lang="stylus" scoped >
  .wrap >>> .swiper-pagination-bullet-active
    background : #fff
  .wrap
    width : 100%
    height : 0
    overflow hidden
    padding-bottom: 32%
    .swiper-img 
      width: 100%;
  


</style>