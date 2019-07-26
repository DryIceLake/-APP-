<template>
<div>
  <home-header :language="language"></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :list="iconsList"></home-icons>
  <recommend-title></recommend-title>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import RecommendTitle from './components/recommend/recomtitle'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    RecommendTitle
  },
  data () {
    return {
      language: '',
      swiperList: [],
      iconsList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.language = data.language
        this.swiperList = data.swiperList
        this.iconsList = data.iconsList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>
