<template>
  <div class="header">
    <div class="header-left">
    厦门
    <span class="iconfont allow-icon">&#xe62d;</span>
    </div>
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
  name: 'HomeHeader'
}
</script>
<style lang="stylus" scoped>
 @import '~styles/varibles.styl';
 .header
   display: flex
   height: .86rem
   line-height: .86rem
   background: $bgColor
   color: #fff
   .header-left
     width: 1.24rem
     float: left
     text-align: center
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
