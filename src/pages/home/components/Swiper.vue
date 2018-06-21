<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
        <swiper-slide v-for="item of swiperList" :key="item.id">
            <img class="swiper-image" :src="item.imgUrl" alt="去哪儿门票">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
    </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  data () {
      return {
          swiperOption: {
              pagination: '.swiper-pagination',
              loop: true,
              autoplay: 1000
          },
          swiperList: [{
              id: '0001',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
          },{
              id: '0002',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e8/14b75b1c81fbe702.jpg_750x200_e6d4f1f1.jpg'   
          }],
      }
  }
};
</script>

<style lang='stylus' scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background #fff
    .wrapper
        width: 100%
        height: 0
        overflow: hidden
        padding-bottom: 26.67%
        background: #eee
        .swiper-image
            width: 100%
</style>


