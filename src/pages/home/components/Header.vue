<template>
<div class="header">
    <div class="header-left" >
        <span class="iconfont bigger">&#xe6f2;</span>
    </div>
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
  props: {
    language: String
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      if (scrollTop <= 200) {
        document.querySelector('.header').style.backgrounColor = `rgba(255,198,6,0)`
      } else {
        document.querySelector('.header').style.backgrounColor = `rgba(255,198,6,1)`
      }
    }
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header {
      width: 100%;
      color: #fff;
      height: .47rem;
      line-height: .47rem;
      display: flex;
      background-color: rgba(255,198,6,0);
      font-size: .14rem;
      position: fixed;
      z-index: 2;
  }
  .header-left {
      width: .4rem;
      float: left;
      margin-right: .1rem;
      margin-left: .1rem;
  }
  .header-input {
      margin-top: .08rem;
      margin-bottom: .08rem;
      flex: 1;
      color: #777;
      background-color: #fff;
      border-radius: .5rem;
      line-height: .31rem;
      opacity: .8;
      padding-left: .1rem;
  }
  .header-right {
      width: .48rem;
      float: right;
      margin-left: .1rem;
      margin-right: .1rem;
      text-align: center;
  }
  .bigger {
      font-size: .2rem;
  }
</style>
