<template>
  <div class="list" >
    <div class="item" v-for="(item, key) of city" :key="key">{{key}}</div>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    city: Object
  }
}
</script>
<style lang="stylus" scoped>
@import "~styles/varibles.styl"
  .list
    position: absolute
    right: 0
    top: 0
    bottom: 0
    width: .42rem
    display: flex
    flex-direction: column
    justify-content:center
    .item
      text-align: center
      line-height: .32rem
      color: $bgColor
</style>
