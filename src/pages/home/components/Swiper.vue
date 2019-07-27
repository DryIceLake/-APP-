<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id"><img class="swiper-img" :src="item.imgUrl"></swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 2000
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: rgba(255,255,255,0.5) !important
    width: 0.09rem !important
  .wrapper >>> .swiper-pagination-bullet
    border-radius: 0
    width: 0.05rem
    height: 0.03rem
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 40%
    background: #eee
  .swiper-img
    width: 100%
    height: 100%
</style>
