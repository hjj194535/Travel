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
  props: {
    iconSwiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: false
      }
    }
  },
  computed: {
    icons () {
      const icons = []
      if (this.iconSwiperList && this.iconSwiperList.length){
        this.iconSwiperList.forEach((item, index) => {
          const icon = Math.floor(index / 8)
          if (!icons[icon]) {
            icons[icon] = []
          }
          icons[icon].push(item)
        })
      }
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
