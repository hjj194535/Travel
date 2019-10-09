<template>
    <swiper :options="swiperOption">
        <swiper-slide v-for="(icon,index) of icons" :key="index">
            <div class="icons">
                <div class="icon" v-for="item of icon" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </div>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      iconSwiperList: [
        {id: '001', imgUrl: 'static/imgs/category/attractions.png', desc: '景点门票'},
        {id: '002', imgUrl: 'static/imgs/category/bingmayong.png', desc: '兵马俑'},
        {id: '003', imgUrl: 'static/imgs/category/bowuguan.png', desc: '博物馆'},
        {id: '004', imgUrl: 'static/imgs/category/garden.png', desc: '动植物园'},
        {id: '005', imgUrl: 'static/imgs/category/hotshow.png', desc: '热门景点'},
        {id: '006', imgUrl: 'static/imgs/category/huaqinggong.png', desc: '华清宫'},
        {id: '007', imgUrl: 'static/imgs/category/huashan.png', desc: '华山'},
        {id: '008', imgUrl: 'static/imgs/category/oneday.png', desc: '一日游'},
        {id: '009', imgUrl: 'static/imgs/category/waterfull.png', desc: '壶口瀑布'}]
    }
  },
  computed: {
    icons () {
      const icons = []
      this.iconSwiperList.forEach((item, index) => {
        const icon = Math.floor(index / 8)
        if (!icons[icon]) {
          icons[icon] = []
        }
        icons[icon].push(item)
      })
      return icons
    }
  }
}
</script>

<style lang="stylus">
    @import '~styles/varibles.styl'
    @import '~styles/mixins.styl'
    .icons
      overflow: hidden
      height: 0
      padding-bottom: 50%
      background: $white
      .icon
        position:relative
        overflow :hidden
        float: left
        width: 25%
        padding-bottom : 23%
        .icon-img
          position: absolute
          top: 0
          left: 0
          right: 0
          bottom: .44rem
          box-sizing: border-box
          padding: .1rem
          .icon-img-content
            display: block
            margin: 0 auto
            height: 100%
        .icon-desc
          position : absolute
          left: 0
          right: 0
          bottom: 0
          height: .44rem
          line-height: .44rem
          text-align: center
          color : $darkTextColor
          ellipsis()
</style>
