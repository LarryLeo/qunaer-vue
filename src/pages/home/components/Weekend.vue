<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item boder-bottom" v-for="item in recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            'http://img1.qunarzz.com/sight/source/1505/19/58f233e11df7ef.jpg_r_640x214_6b42c9fc.jpg',
          title: '西安必游TOP10',
          desc: '寻长安梦，开启穿越的圆梦之旅'
        },
        {
          id: '0002',
          imgUrl:
            'http://img1.qunarzz.com/sight/source/1511/14/1cf5dc2ecbfc16.jpg_r_640x214_b4b3a58a.jpg',
          title: '最美丝路行',
          desc: '情系西北，中国梦丝路行'
        },
        {
          id: '0003',
          imgUrl:
            'http://img1.qunarzz.com/sight/source/1509/2f/bbb38e80bf749f.jpg_r_640x214_2590c69d.jpg',
          title: '唐诗里的秋天',
          desc: '秋日赏枫，梦幻枫叶的天堂'
        },
        {
          id: '0004',
          imgUrl:
            'http://img1.qunarzz.com/sight/source/1507/98/d9c848b0d7d65a.jpg_r_640x214_55778a01.jpg',
          title: '就是爱大自然',
          desc: '这个周末爬爬山，呼吸呼吸新鲜空气'
        },
        {
          id: '0005',
          imgUrl:
            'http://img1.qunarzz.com/sight/source/1507/fe/679926851c309a.jpg_r_640x214_114816de.jpg',
          title: '不一样的周末',
          desc: '这个周末玩点不一样的'
        }
      ]
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
  padding-bottom 33.9%

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
