<template>
  <div class="header">
    <div class="left">
      <div class="iconfont back-icon">&#xe62d;</div>
    </div>
    <div class="input">
      <span class="iconfont">&#xe621;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe60c;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
// 引入变量
@import '../../../assets/styles/variables.styl'

.header
  display flex
  background-color $bgColor
  color #fff
  line-height 0.86rem

  .left
    width 0.64rem
    float left

    .back-icon
      text-align center
      font-size 0.4rem

  .input
    flex 1
    height 0.64rem
    line-height 0.64rem
    padding-left 0.2rem
    margin-top 0.12rem
    margin-bottom 0.12rem
    background-color #fff
    color #ccc
    border-radius 0.1rem

  .right
    width 1.24rem
    color #fff
    float right
    text-align center

    .arrow-icon
      font-size 0.32rem
</style>
