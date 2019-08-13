<template>
  <div>
    <router-link
      tag="div"
      to="/"
      class="header-back"
      v-show="showBack"
    >
      <div class="iconfont">&#xe624;</div>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showBack"
      :style="opacityStyle"
    >
      <div class="header">
        景点详情
        <router-link to="/">
        <div class="iconfont left">&#xe624;</div>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showBack: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {opacity}
        this.showBack = false
      } else {
        this.showBack = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-back
    position: absolute
    top: .2rem
    left: .2rem
    width: .7rem
    height: .7rem
    line-height: .7rem
    border-radius: .5rem
    background: rgba(0, 0, 0, .5)
    color: #fff
    font-size: .5rem
    text-align: center
  .header-fixed
    position: fixed
    top 0
    left 0
    right 0
    height: $headerHeight
    line-height: $headerHeight
    overflow: hidden
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    .left
      position: absolute
      left: 0
      top: 0
      width: .64rem
      text-align: center
      font-size: .35rem
      color: #fff
</style>
