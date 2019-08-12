<template>
  <div>
    <div class="banner" @click="handleClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1901/d2/d20386fec7943deba3.img.jpg_600x330_ed99f76c.jpg"/>
      <div class="banner-info">
        <div class="banner-title">
          厦门科技馆
        </div>
        <div class="banner-number">
          <span class="iconfont">&#xe678;</span>
            35
        </div>
      </div>
    </div>
    <common-gallery
      :imgs="imgs"
      v-show="showGallery"
      @close='handleGralleryClose'
    >
    </common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1901/d2/d20386fec7943deba3.img.jpg_r_800x800_8aea5d0c.jpg', 'http://img1.qunarzz.com/sight/p0/1905/3b/3b1280195d70e22a3.water.jpg_r_800x800_a1b62d08.jpg']
    }
  },
  methods: {
    handleClick () {
      this.showGallery = true
    },
    handleGralleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    height: 0
    overflow: hidden
    padding-bottom: 55%
    position: relative
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .7))
      .banner-title
        color: #fff
        font-size: .36rem
        padding-left: .2rem
        flex:1
      .banner-number
        height: .36rem
        line-height: .36rem
        color: #fff
        margin:.12rem .1rem 0 0
        font-size: .24rem
        background: rgba(0 ,0 ,0 ,.5)
        border-radius: .2rem
        padding: 0 .2rem
</style>
