<template>
  <ul class="list">
    <li class="item" v-for="(item, key) in cities" :key="key">{{key}}</li>
  </ul>
</template>
<script>
export default {
  props: {
    cities: Object
  },
  name: 'CityAlphabet'
}
</script>
<style lang="stylus" scoped>
@import '../../../assets/styles/variables.styl'

.list
  display flex
  flex-direction column
  justify-content center
  position absolute
  top 1.58rem
  right 0
  bottom 0
  width 0.4rem

  .item
    text-align center
    line-height 0.4rem
    color $bgColor
</style>
