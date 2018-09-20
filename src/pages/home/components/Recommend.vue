<template>
  <div>
    <div class="title">
      <img class="title-icon" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png">
      热销推荐
    </div>
    <ul>
      <router-link
        :to="'/detail/' + item.id"
        tag="li"
        class="item border-bottom"
        v-for="item of list"
        :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
    }
  },
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    position: relative;
    line-height: .8rem;
    background-color: #f1f1f1;
    text-indent: .2rem;
    padding-left: .5rem;
    .title-icon
      position: absolute;
      top: .2rem;
      left: .2rem;
      width: .4rem;
      height: .4rem;
  .item
    overflow: hidden;
    display: flex;
    height: 1.9rem;
    .item-img
      width: 1.7rem;
      height: 1.7rem;
      padding: .1rem;
    .item-info
      flex: 1;
      min-width: 0;
      padding: .1rem;
      .item-title
        line-height: .54rem;
        font-size: .32rem;
        ellipsis();
      .item-desc
        line-height: .4rem;
        color: #aaa;
        ellipsis();
      .item-button
        line-height: .44rem;
        margin-top: .16rem;
        background-color: #ff9300;
        margin-top: .2rem;
        padding: 0 .2rem;
        border-radius: .06rem;
        color: #fff;
</style>
