<template>
 <div class="wrapper">
  <swiper :options="swiperOption" >
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.url">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
 </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      list: [{
        id: '001',
        url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/87a224d0349d94a11e97f31aa1aba4f5.jpg_750x200_1f78af87.jpg'
      }, {
        id: '002',
        url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/d7bbc21db442366a882e04ddc984669a.jpg_750x200_85e640d9.jpg'
      }, {
        id: '003',
        url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/025aaafa0fc7828dbc87bbbd8f065eff.jpg_750x200_c8e29266.jpg'
      }, {
        id: '004',
        url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/2a9d5a82ec256e65950c45a878050e69.jpg_750x200_306d2f6f.jpg'
      }, {
        id: '005',
        url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/c496c451a7d71cc36457fc81c40f5b41.jpg_750x200_f7f6bced.jpg'
      }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
 background: rgba(255,255,255,1)
.wrapper
 overflow:hidden
 width:100%
 height:0
 padding-bottom:26.6667%
 .swiper-img
  width:100%
</style>
