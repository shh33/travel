<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"
          v-for="item of page"
          :key='item.id'
        >
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgURL">
          </div>
          <p class="icon-text">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '001',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '002',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '亲子游'
      }, {
        id: '003',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '厦门必游'
      }, {
        id: '004',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
        desc: '鼓浪屿'
      }, {
        id: '005',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      }, {
        id: '006',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
        desc: '主题乐园'
      }, {
        id: '007',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        desc: '动植物园'
      }, {
        id: '008',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
        desc: '展馆展览'
      }, {
        id: '009',
        imgURL: 'https://imgs.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
        desc: '游船观光'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
    overflow: hidden
    width:100%
    height: 0
    padding-bottom: 50%
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      padding-bottom: 25%
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
