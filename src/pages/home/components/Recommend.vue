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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1412/89/66dadfb4d982e6f88abad45a3e062342.water.jpg_200x200_0443bc40.jpg',
          title: '曲江海洋极地公园',
          desc: '极地公园四馆八区带你畅游海洋世界'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/db/dbd0bef45fbc36b3.img.jpg_200x200_1b88abcf.jpg',
          title: '大唐芙蓉园',
          desc: '中国最大的仿唐皇家建筑群'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1411/1a/5582f9f24bc50b475a8cbda4c5ac8d24.water.jpg_200x200_a0d48950.jpg',
          title: '秦始皇陵博物院（兵马俑）',
          desc: '古墓稀世珍宝，世界第八大奇迹'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/12/1207d28c272c5864.water.jpg_200x200_30119788.jpg',
          title: '翠华山',
          desc: '太乙真人修炼地，李世民避暑消夏'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1610/2d/2d6480f93f464e0a3.img.jpg_200x200_51908dc5.jpg',
          title: '白鹿原影视城',
          desc: '远望关口、身在关中'
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
