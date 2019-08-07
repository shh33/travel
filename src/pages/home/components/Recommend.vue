<template>
  <div class="Recommend">
    <div class="title">猜你喜欢</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key='item.id'>
        <img class="item-img" :src="item.src">
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
      recommendList: [{
        src: 'http://img1.qunarzz.com/sight/p0/1901/d2/d20386fec7943deba3.img.jpg_200x200_6c120222.jpg',
        id: '001',
        title: '厦门科技馆',
        desc: '厦门科技馆让科学变好玩'
      }, {
        src: 'http://img1.qunarzz.com/sight/p0/1901/d2/d20386fec7943deba3.img.jpg_200x200_6c120222.jpg',
        id: '002',
        title: '厦门科技馆',
        desc: '厦门科技馆让科学变好玩'
      }, {
        src: 'http://img1.qunarzz.com/sight/p0/1901/d2/d20386fec7943deba3.img.jpg_200x200_6c120222.jpg',
        id: '003',
        title: '厦门科技馆',
        desc: '厦门科技馆让科学变好玩'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    line-height .8rem
    background: #eee
    text-indent: .2rem
  .item
    padding: 10px
    display: flex
    height: 2rem
    .item-img
      width: 2rem
      height: 2rem
    .item-info
      flex: 1
      padding: .2rem
      min-width: 0
      .item-title
        ellipsis()
        line-height: .54rem
        font-size: .32rem
      .item-desc
        ellipsis()
        line-height: .4rem
        color: #9e9e9e
      .item-button
        line-height: .44rem
        background: #ff9300
        color: #fff
        padding: 0 .15rem
        margin-top: .2rem
        border-radius: .06rem
</style>
