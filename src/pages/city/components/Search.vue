<template>
  <div>
    <div class="search">
      <input
       v-model="keyword"
          class="search-input"
          type="text"
          placeholder="请输入城市名或拼音"
      >
    </div>
    <div
      class="search-content"
      ref="wrapper"
      v-show="keyword"
    >
      <ul>
        <li
          class="search-item border-bottom"
          v-for="item in list"
          :key="item.id"
          @click="handleCityClick(item.name)"
        >
          {{item.name}}
        </li>
        <li
          class="search-item border-bottom"
          v-show="hasNoData"
        >
        没有找到对应的数据
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import { mapMutations } from 'vuex'
import BScroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    city: Object
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.city) {
          this.city[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  methods: {
    handleCityClick (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      padding: 0 .4rem
      border-radius: .06rem
      text-align: center
      top: 0
      color: #666
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: .6rem
      padding-left: .2rem
      background: #fff
      color: #666
</style>
