<template>
  <div class="header">
    <router-link to="/">
       <div>
         <span class="arrow"></span>
       </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'GoodsHeader'
}
</script>
<style lang="stylus" scoped>
  .header {
    width: 100%;
    color: #fff;
    height: 0.47rem;
    line-height: 0.47rem;
    display: flex;
    background-color: #fff;
    font-size: 0.14rem;
    position: fixed;
    z-index: 2;
  }
  .arrow {
    display: inline-block;
    width: 8px;
    height: 8px;
    border-bottom: 3px solid #ccc;
    border-left: 3px solid #ccc;
    transform: rotate(45deg);
    position: absolute;
    right: 15px;
    top: 5px;
  }
</style>
