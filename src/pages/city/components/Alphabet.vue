<template>
  <div class="list">
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet'
}
</script>
<style lang="stylus" scoped>
  .list
    position: absolute
    right: 0
    top: 0
    bottom: 0
    width: .4rem
    display: flex
    flex-direction: column
    justify-content:center
    .item
      text-align: center
      line-height: .35rem
</style>
