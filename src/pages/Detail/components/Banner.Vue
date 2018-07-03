<template>
    <div class="banner">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_600x330_cd2e3bf7.jpg" />
        <div class="banner-info">
            <div class="banner-title">广州长隆旅游度假区</div>
            <div class="banner-number"><span class="iconfont banner-icon">&#xe678;</span>16</div>
        </div>
    </div>   
</template>

<script>
export default {
    name: 'detailBanner'
}
</script>

<style lang="stylus" scoped>
    .banner
        position relative
        overflow hidden
        height 0
        padding-bottom 55%
        .banner-img
            width 100%
        .banner-info
            display flex
            position absolute
            left 0
            right 0
            bottom 0
            line-height .6rem
            color #fff
            background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
            .banner-title
                font-size .32rem
                padding 0 .2rem
                flex 1
            .banner-number
                margin-top .14rem
                padding 0 .4rem
                height .32rem
                line-height .32rem
                border-radius .2rem
                background rgba(0,0,0,.8)
                font-size .24rem
                .banner-icon
                    font-size .24rem
                    padding-right .1rem
</style>

