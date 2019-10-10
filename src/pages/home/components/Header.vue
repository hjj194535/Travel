<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont iconfanhui"></span>
        </div>
        <div class="header-input">
          <span class="iconfont iconsousuo"></span>
          输入城市/景点/游玩/主题
        </div>
        <router-link to="/city">
          <div class="header-right">
            {{this.city}}
            <span class="iconfont iconsanjiaoxing header-right-triangle"></span>
          </div>
        </router-link>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display:flex
    line-height:$headerHeight
    background :$headerColor
    color:$white
    
    .header-left
      width:.64rem
      float:left
      text-align :center

    .header-input
      flex :1
      line-height: .64rem
      height:.64rem
      margin-left:.2rem
      margin-top:.12rem
      border-radius: .1rem
      background:$white
      color: #ccc
      text-indent :.2rem

    .header-right
      width:1.24rem
      float:right
      text-align:center
      color: $white
      .header-right-triangle
        font-size:.06rem

</style>
