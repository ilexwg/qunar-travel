<template>
  <div class="header">
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <router-link tag="div" to="/" class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <div class="iconfont header-fixed-back">&#xe624;</div>
      景点详情
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header-abs
    position: absolute;
    left: .2rem;
    top: .2rem;
    width: .8rem;
    height: .8rem;
    line-height: .8rem;
    border-radius: .4rem;
    background-color: rgba(0, 0, 0, .8);
    text-align: center;
    .header-abs-back
      color: #fff;
      font-size: .4rem;
  .header-fixed
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 2;
    height: $headerHeight;
    line-height: $headerHeight;
    text-align: center;
    color: #fff;
    background-color: $bgColor;
    font-size: .32rem;
    .header-fixed-back
      position: absolute;
      top: 0;
      left: 0;
      width: .65rem;
      text-align: center;
      font-size: .4rem;
      color: #fff;
</style>
