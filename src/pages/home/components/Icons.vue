<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of list" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      if (this.list) {
        this.list.forEach((item, index) => {
          const page = Math.floor(index / 10)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
      }
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  @import '~styles/mixins.styl';
  .icons >>> .swiper-container
    overflow: hidden
    height: 0
    padding-bottom: 55%
    background-color: #fff;
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 20%
    height: 0
    padding-bottom: 20%
    margin-top: 5%
  .icon-img
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: .22rem
    box-sizing: border-box
  .icon-img-content
    width: 60%
    height: 85%
    margin: 0 auto
  .icon-desc
    position: absolute
    bottom: 0
    left: 0
    right: 0
    height: .22rem
    line-height: .22rem
    color: $darkText
    font-size: .14rem
    text-align: center
    ellipsis()
</style>
