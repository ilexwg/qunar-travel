<template>
  <div>
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          title: '寻找北京的皇城范儿',
          desc: '数百年的宫廷庙宇，至今依旧威严霸气'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
          title: '北京清凉避暑胜地',
          desc: '到大自然中享受“天然空调”的清凉'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          title: '北京必游TOP10',
          desc: '来北京必去的景点非这些地方莫属'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem;
    background-color: #f1f1f1;
    text-indent: .2rem;
  .item-img-wrapper
    overflow: hidden;
    height: 0;
    padding-bottom: 37.09%;
    .item-img
      width: 100%;
  .item-info
    padding: .1rem;
    .item-title
      line-height: .54rem;
      font-size: .32rem;
      ellipsis();
    .item-desc
      line-height: .4rem;
      color: #aaa;
      ellipsis();
</style>
