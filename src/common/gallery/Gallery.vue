<template>
  <div class="containner" @click="handleGalleryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide
          v-for="(item, index) in imgs"
          :key="index"
        >
          <img class="swiper-img" :src="item">
        </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CommonGallery',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .containner >>> .swiper-container
    overflow: inherit
  .containner
    z-index: 10
    position: fixed
    display: flex
    flex-direction: column
    justify-content: center
    top: 0
    left: 0
    right: 0
    bottom: 0
    background: #000
    .wrapper
      width: 100%
      height 0
      padding-bottom: 100%
      .swiper-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -40%
</style>
