<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item boder-bottom" v-for="item in recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img
            :src="item.imgUrl"
            alt=""
            class="item-img"
          >
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  },
  data () {
    return {
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '../../../assets/styles/mixin.styl'

.recommend-title
  margin-top 0.2rem
  line-height 0.8rem
  text-indent 0.2rem
  background-color #eee

.item
  overflow hidden
  display flex
  height 1.9rem

  .item-img
    width 1.7rem
    height 1.7rem
    padding 0.1rem

  .item-info
    flex 1
    padding 0.1rem

    .item-title
      ellipsis()
      line-height 0.54rem
      font-size 0.32rem

    .item-desc
      ellipsis()
      line-height 0.4rem
      min-width 0
      color #ccc

    .item-button
      line-height 0.44rem
      margin-top 0.16rem
      background #ff9300
      padding 0 0.2rem
      border-radius 0.06rem
      color #fff
</style>
