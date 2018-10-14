<template>
  <div>
    <div class="search">
      <input type="text" placeholder="请输入城市名或拼音" class="search-input" v-model="keyword">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li
          class="search-item border-bottom"
          v-for="(item, index) in resultList"
          :key="index"
        >{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      resultList: [],
      time: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.resultList = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.resultList = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.resultList.length
    }
  }
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

.search-content
  position absolute
  z-index 1
  overflow hidden
  top 1.58rem
  left 0
  right 0
  bottom 0
  background #eee

  .search-item
    line-height 0.62rem
    padding-left 0.2rem
    background-color #fff
    color #666
</style>
