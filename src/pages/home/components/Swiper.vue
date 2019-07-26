<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id"><img class="swiper-img" :src="item.imgUrl"></swiper-slide>
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
        loop: true,
        autoplay: 2000
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://image2.suning.cn/uimg/aps/material/155058120028429292.jpg'
      }, {
        id: '0002',
        imgUrl: "https://image1.suning.cn/uimg/aps/material/156371100357707416.jpg"
      }, {
        id: '0003',
        imgUrl: 'https://image2.suning.cn/uimg/aps/material/155058120060465377.jpg'
      }]
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
    padding-bottom: 50%
    background: #eee
  .swiper-img
    width: 100%
    height: 100%
</style>
