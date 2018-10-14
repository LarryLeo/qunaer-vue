<template>
  <ul class="list">
    <li
      class="item"
      v-for="item in letters"
      :key="item"
      :ref="item"
      v-on:click="handleLetterClick"
      @touchstart="handelTouchStart"
      @touchmove="handelTouchMove"
      @touchend="handelTouchEnd"
    >{{item}}</li>
  </ul>
</template>
<script>
export default {
  props: {
    cities: Object
  },
  name: 'CityAlphabet',
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
    // 只会在接收到cities数据时执行，因此不必在touchmove事件中多次获取offsetTop，从而提高了性能
  },
  computed: {
    letters () {
      const letters = []
      // 循环对象
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handelTouchStart () {
      this.touchStatus = true
    },
    handelTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        // 为提升性能，所以这里用了setTimeout，暂时还不是太清楚原理
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 80 // 本来距离顶部搜索框高度应该是74，但是为了能让index从0开始，加了6像素，这样取余就能有0了，否则letterIndex始终只能以1开头
          const letterIndex = Math.floor((touchY - this.startY) / 20)
          if (letterIndex >= 0 && letterIndex < this.letters.length) {
            this.$emit('change', this.letters[letterIndex])
          }
        }, 16)
      }
    },
    handelTouchEnd () {
      this.touchStatus = false
    }
  }
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
