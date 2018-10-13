<template>
  <div class="header">城市选择
    <router-link to="/">
      <div class="iconfont back-icon">&#xe62d;</div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '../../../assets/styles/variables.styl'

.header
  position relative
  height 0.86rem
  line-height 0.86rem
  overflow hidden
  text-align center
  color #fff
  font-size 0.32rem
  background-color $bgColor

.back-icon
  position absolute
  top 0
  left 0
  width 0.64rem
  font-size 0.4rem
  text-align center
  color #fff
</style>
