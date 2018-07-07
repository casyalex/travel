<template>
    <div class="list" ref="wrapper">
        <div class="content">
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">
                            {{this.currentCity}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hotCities" :key="item.id" @click="handleCityClick(item.name)">
                        <div class="button">
                            {{item.name}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" 
                    v-for="innerItem of item" 
                    :key="innerItem.id" @click="handleCityClick(innerItem.name)">
                        {{innerItem.name}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Bscroll from "better-scroll";
import { mapState, mapMutations } from 'vuex';
export default {
  name: "CityList",
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  computed: {
      ...mapState({
          currentCity: 'city'
      })
  },
  methods: {
    handleCityClick(city) {
      this.changeCity(city);
      this.$router.push("/");
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter() {
      if (this.letter) {
        const ele = this.$refs[this.letter][0];
        this.scroll.scrollToElement(ele);
      }
    }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper,{
        mouseWheel: true,
        click: true,
        tap: true
    });
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.border-topbottom {
    &:before {
        border-color: #cccccc;
    }

    &:after {
        border-color: #cccccc;
    }
}

.border-bottom {
    &:before {
        border-color: #cccccc;
    }
}

.list {
    position: absolute;
    overflow: hidden;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;

    .title {
        line-height: 0.54rem;
        background: #eeeeee;
        padding-left: 0.2rem;
        color: #666;
        font-size: 0.26rem;
    }

    .button-list {
        overflow: hidden;
        padding: 0.1rem 0.6rem 0.1rem 0.1rem;

        .button-wrapper {
            float: left;
            width: 33%;

            .button {
                padding: 0.1rem 0;
                margin: 0.1rem;
                text-align: center;
                border: 0.02rem solid #ccc;
                border-radius: 0.06rem;
            }
        }
    }

    .item-list {
        .item {
            line-height: 0.76rem;
            color: #666666;
            padding-left: 0.2rem;
        }
    }
}
</style>

