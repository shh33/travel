<template>
  <div class="Recommend">
    <div class="title">周末去哪儿</div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key='item.id'
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.src">
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
      recommendList: [{
        src: 'http://img1.qunarzz.com/sight/source/1711/15/1cdd5ee885686b.jpg_r_640x214_46768064.jpg',
        id: '001',
        title: '厦门科技馆',
        desc: '厦门科技馆让科学变好玩'
      }, {
        src: 'http://img1.qunarzz.com/sight/source/1505/b3/671f666cc7845a.jpg_r_640x214_f977f30c.jpg',
        id: '002',
        title: '厦门科技馆',
        desc: '厦门科技馆让科学变好玩'
      }, {
        src: 'http://img1.qunarzz.com/sight/source/1511/8f/bf3a40e4afcf29.jpg_r_640x214_90225212.jpg',
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
  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 33.4%
    background: pink
  .item-img
    width: 100%
  .item-info
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
</style>
