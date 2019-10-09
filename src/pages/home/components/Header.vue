<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont iconfanhui"></span>
        </div>
        <div class="header-input">
          <span class="iconfont iconsousuo"></span>
          输入城市/景点/游玩/主题
        </div>
        <div class="header-right">
          城市
          <span class="iconfont iconsanjiaoxing header-right-triangle"></span>
        </div>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display:flex
    line-height:.86rem
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
      .header-right-triangle
        font-size:.06rem

</style>
