<template>
  <div class="header" :class="[{ 'header-backcolor0': !scrollFlag },{ 'header-backcolor1': scrollFlag }]">
    <router-link to="/goods">
      <div class="header-left">
        <span class="iconfont bigger">&#xe6f2;</span>
      </div>
    </router-link>
    <div class="header-input">
      <span class="iconfont">&#xe62d;</span>
      {{this.language}}
    </div>
    <div class="header-right">登录</div>
  </div>
  </template>

<script>
export default {
  name: 'HomeHeader',
  data () {
    return {
      scrollFlag: false
    }
  },
  props: {
    language: String
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      let _this = this
      var scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop
      if (scrollTop) {
        _this.scrollFlag = true
      } else {
        _this.scrollFlag = false
      }
    }
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  width: 100%;
  color: #fff;
  height: 0.47rem;
  line-height: 0.47rem;
  display: flex;
  font-size: 0.14rem;
  position: fixed;
  z-index: 2;
}

.header-backcolor0 {
  background-color: rgba(255, 198, 6, 0);
}

.header-backcolor1 {
  background-color: rgba(255, 198, 6, 1);
}

.header-left {
  width: 0.4rem;
  float: left;
  margin-right: 0.1rem;
  margin-left: 0.1rem;
  color: #fff;
}

.header-input {
  margin-top: 0.08rem;
  margin-bottom: 0.08rem;
  flex: 1;
  color: #777;
  background-color: #fff;
  border-radius: 0.5rem;
  line-height: 0.31rem;
  opacity: 0.8;
  padding-left: 0.1rem;
}

.header-right {
  width: 0.48rem;
  float: right;
  margin-left: 0.1rem;
  margin-right: 0.1rem;
  text-align: center;
}

.bigger {
  font-size: 0.2rem;
}
</style>
