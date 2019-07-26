<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide><img src="https://image2.suning.cn/uimg/aps/material/155058120028429292.jpg"></swiper-slide>
      <swiper-slide><img src="https://image3.suning.cn/uimg/cms/img/156395130619847894.jpg"></swiper-slide>
      <swiper-slide><img src="https://image2.suning.cn/uimg/aps/material/155058120060465377.jpg"></swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {}
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 50%
  .swiper-img
    width: 100%
</style>
