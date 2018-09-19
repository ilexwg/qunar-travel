<template>
  <div>
    <div class="title">
      <img class="title-icon" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png">
      热销推荐
    </div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '故宫故宫故宫故宫故宫故宫故宫故宫故宫'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg',
          title: '北京欢乐谷',
          desc: '北京欢乐谷北京欢乐谷北京欢乐谷'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
          title: '北京野生动物园',
          desc: '北京野生动物园北京野生动物园'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_200x200_444cc7e8.jpg',
          title: '圆明园',
          desc: '圆明园圆明园圆明园圆明园圆明园'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/c8/c88bb5e69c9a9c5ea3.img.jpg_200x200_740720ff.jpg',
          title: '古北水镇',
          desc: '古北水镇古北水镇古北水镇古北水镇'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_200x200_c62292e9.jpg',
          title: '北京动物园',
          desc: '北京动物园北京动物园北京动物园'
        }
      ]
    }
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
