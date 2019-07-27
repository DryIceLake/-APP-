<template>
  <div>
    <recommend-title></recommend-title>
    <space-px></space-px>
    <recommend-small></recommend-small>
  </div>
</template>
<script>
import SpacePx from './recommend/SpacePx'
import RecommendTitle from './recommend/recomtitle'
import RecommendBody from './recommend/RecommendBody'
import RecommendSmall from './recommend/RecommendSmall'
export default {
  name: 'Recommend',
  components: {
    SpacePx,
    RecommendTitle,
    RecommendBody,
    RecommendSmall
  }
}
</script>
<style lang="stylus" scoped>
</style>
