<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swiper-image" :src="item.imgUrl" alt="去哪儿门票">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
      list: Array
  },
  data () {
      return {
          swiperOption: {
              pagination: '.swiper-pagination',
              loop: true,
              autoplay: 1500
          },
      }
  },
  computed: {
      showSwiper () {
          return this.list.length
      }
  }
};
</script>

<style lang='stylus' scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background #fff
    .wrapper >>> .swiper-pagination-bullets
        bottom 5px
    .wrapper
        width: 100%
        height: 0
        overflow: hidden
        padding-bottom: 30.8%
        background: #eee
        .swiper-image
            width: 100%
</style>


