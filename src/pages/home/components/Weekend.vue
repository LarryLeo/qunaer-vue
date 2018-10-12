<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item boder-bottom" v-for="item in weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl" alt="" class="item-img">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
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

.item-img-wrapper
  height 0
  overflow hidden
  padding-bottom 37.09%

.item-img
  width 100%

.item-info
  padding-bottom 0.24rem

.item-title
  ellipsis()
  line-height 0.54rem
  font-size 0.32rem

.item-desc
  ellipsis()
  line-height 0.4rem
  min-width 0
  color #ccc
</style>
