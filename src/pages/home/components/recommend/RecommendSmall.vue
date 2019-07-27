<template>
  <div class="icons-div">
      <div class="recom-text">
        <p class="first">1111111111</p>
        <p class="second">2</p>
      </div>
      <div class="recom-img">
        <img src="https://image1.suning.cn/uimg/cms/img/156317651546760648.png">
      </div>
  </div>
</template>
<script>
export default {
  name: 'RecommendTitle'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  .icons-div
    divstyle2()
    margin-left: 5%
    border-top-left-radius: 20%
  .recom-text
    width: 100%
    height: 30%
  .first
    recomTitle()
    ellipsis()
  .second
    recomText()
    ellipsis()
  .recom-img
    recomImg()
</style>
