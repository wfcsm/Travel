<template>
  <div class="wrap">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(item) of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.url">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination" ></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
    return {
      swiperOption: {
        //notNextTick是一个组件自有属性，
        //如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，
        //也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
        notNextTick: true,
        loop: true,
        pagination: '.swiper-pagination'
      },
      swiperList: [
        {
          id: '001',
          url:
            'http://img1.qunarzz.com/piao/fusion/1812/a9/eda2ca8c654a0102.jpg_750x200_a5b562f1.jpg'
        },
        {
          id: '002',
          url:
            'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'
        },
        {
          id: '003',
          url:
            'http://img1.qunarzz.com/piao/fusion/1609/d7/f583f33b4a246e02.jpg_750x200_139d4b0c.jpg'
        },
        {
          id: '004',
          url:
            'http://img1.qunarzz.com/piao/fusion/1812/7e/8da342fdf0fc902.jpg_750x200_8a8baecd.jpg'
        },
        {
          id: '005',
          url:
            'http://img1.qunarzz.com/piao/fusion/1609/d7/f583f33b4a246e02.jpg_750x200_139d4b0c.jpg'
        },
        {
          id: '006',
          url:
            'http://img1.qunarzz.com/piao/fusion/1609/4d/3dc09bcc290f0c02.jpg_750x200_09c97d67.jpg'
        },
        {
          id: '007',
          url:
            'http://img1.qunarzz.com/piao/fusion/1811/31/da037478f37cf202.jpg_750x200_fe28d396.jpg'
        },
        {
          id: '008',
          url:
            'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'
        }
      ]
    };
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper;
    }
  }
};
</script>

<style lang="stylus" scoped >
  .wrap
    width : 100%
    height : 0
    overflow hidden
    padding-bottom: 26.25%
    .swiper-img 
      width: 100%;
  


</style>