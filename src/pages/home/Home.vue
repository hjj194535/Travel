<template>
    <div class="home">
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <hot-list></hot-list>
        <interested></Interested>
        <weekend></weekend>
    </div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HotList from './components/Hotlist'
import Interested from './components/Interested'
import Weekend from './components/Weekend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HotList,
    Interested,
    Weekend

  }
}
</script>

<style lang="stylus">
  @import '~styles/common.styl'
  @import '~styles/varibles.styl'
  .home
    background-color: $bgColor
</style>
