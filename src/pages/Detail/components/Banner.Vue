<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_600x330_cd2e3bf7.jpg" />
            <div class="banner-info">
                <div class="banner-title">广州长隆旅游度假区</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe678;</span>16</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGalleryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from "common/gallary/Gallary";
export default {
  name: "detailBanner",
  data () {
      return {
          showGallary: false,
          imgs:['http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_r_800x800_41637b9b.jpg',
          'http://img1.qunarzz.com/sight/p0/201403/07/452bd2d46925768793ff15a853899211.jpg_r_800x800_351f3cc7.jpg']
      }
  },
  methods: {
      handleBannerClick () {
          this.showGallary = true
      },
      handleGalleryClose () {
          this.showGallary = false
      }
  },
  components: {
    CommonGallary
  }
};
</script>

<style lang="stylus" scoped>
.banner {
    position: relative;
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;

    .banner-img {
        width: 100%;
    }

    .banner-info {
        display: flex;
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        line-height: 0.6rem;
        color: #fff;
        background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));

        .banner-title {
            font-size: 0.32rem;
            padding: 0 0.2rem;
            flex: 1;
        }

        .banner-number {
            margin-top: 0.14rem;
            padding: 0 0.4rem;
            height: 0.32rem;
            line-height: 0.32rem;
            border-radius: 0.2rem;
            background: rgba(0, 0, 0, 0.8);
            font-size: 0.24rem;

            .banner-icon {
                font-size: 0.24rem;
                padding-right: 0.1rem;
            }
        }
    }
}
</style>

