<template>
<div>
  <home-header :language="language"></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :list="iconsList"></home-icons>
  <ad-component></ad-component>
  <ad-imagation></ad-imagation>
  <blank-bar></blank-bar>
  <recommend></recommend>
</div>
</template>

<script>
import BlankBar from './components/BlankBar'
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import AdComponent from './components/AdComponent'
import AdImagation from './components/AdImagation'
import Recommend from './components/Recommend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    Recommend,
    AdComponent,
    AdImagation,
    BlankBar
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
