<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"
          v-for="item of page"
          :key='item.id'
        >
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-text">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
  .icons
    padding-top: .1rem
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons >>> .swiper-pagination-bullet-active
    background: $bgColor
  .icons >>> .swiper-pagination-bullet
    width: 6px;
    height: 6px;
  .swiper-pagination-bullets
    bottom: 5px
  .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      padding-bottom: 23%
      .icon-img
        box-sizing: border-box
        position: absolute
        left: 0
        top: 0
        right: 0
        bottom: .44rem
        padding: .1rem
        .icon-img-content
          margin: 0 auto
          height: 100%
          display: block
      .icon-text
        position: absolute
        bottom: 0
        height: .44rem
        line-height: .44rem
        width: 100%
        text-align: center
        color: $darkTextColor
        ellipsis()
</style>
