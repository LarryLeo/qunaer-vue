<template>
  <div class="search">
    <input type="text" placeholder="请输入城市名或拼音" class="search-input">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>
<style lang="stylus" scoped>
@import '../../../assets/styles/variables.styl'

.search
  height 0.72rem
  background-color $bgColor
  padding 0 0.1rem

  .search-input
    box-sizing border-box
    height 0.62rem
    line-height 0.62rem
    width 100%
    text-align center
    border-radius 0.06rem
    color #666
    padding 0 0.1rem
</style>
