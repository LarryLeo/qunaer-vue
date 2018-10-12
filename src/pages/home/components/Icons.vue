<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img :src="item.imgUrl" alt="" class="icon-img-content">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconsList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconsList.forEach((item, index) => {
        let page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/variables.styl'
@import '../../../assets/styles/mixin.styl'

.icons
  margin-top 0.2rem

.icons >>> .swiper-container
  width 100%
  height 0
  padding-bottom 55%

  .icon
    position relative
    float left
    width 25%
    overflow hidden
    height 0
    padding-bottom 25%

    .icon-img
      position absolute
      top 0
      left 0
      right 0
      bottom 0.24rem
      box-sizing border-box
      padding-bottom 0.1rem

      .icon-img-content
        height 100%
        display block
        margin 0 auto

    .icon-desc
      ellipsis()
      position absolute
      left 0
      right 0
      bottom 0
      text-align center
      line-height 0.44rem
      height 0.44rem
      color $darkTextColor
</style>
