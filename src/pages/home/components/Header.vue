<template>
  <div class="header">
    <router-link to="/city">
      <div class="header-left">
      {{this.city}}
      <span class="iconfont allow-icon">&#xe62d;</span>
    </div>
    </router-link>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
    </div>
    <div class="header-right">
      <span class="iconfont">&#xe639;</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
 @import '~styles/varibles.styl';
 .header
   display: flex
   height: $headerHeight
   line-height: $headerHeight
   background: $bgColor
   color: #fff
   .header-left
     width: 1.24rem
     float: left
     text-align: center
     color: #fff
     .allow-icon
      font-size: .3rem
   .header-input
     padding-left: .2rem
     flex: 1
     background: #fff
     height: .64rem
     line-height: .64rem
     margin-top: .11rem
     border-radius: .3rem
     color:#ccc
   .header-right
     width: .86rem
     text-align:center
     float: right
</style>
