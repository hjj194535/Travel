<template>
    <div class="home">
        <home-header :city="city"></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :iconSwiperList="iconSwiperList"></home-icons>
        <hot-list :hotList="hotList"></hot-list>
        <interested :likeList="likeList"></Interested>
        <weekend :weekendTripList="weekendTripList"></weekend>
    </div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HotList from './components/Hotlist'
import Interested from './components/Interested'
import Weekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HotList,
    Interested,
    Weekend
  },
  data () {
    return {
      city: '',
      hotList: [],
      iconSwiperList: [],
      likeList: [],
      swiperList: [],
      weekendTripList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.errCode == '200' && res.data){
        let data = res.data
        this.city = data.city
        this.hotList = data.hotList
        this.iconSwiperList = data.iconSwiperList
        this.likeList = data.likeList
        this.swiperList = data.swiperList
        this.weekendTripList = data.weekendTripList
      }

    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus">
  @import '~styles/common.styl'
  @import '~styles/varibles.styl'
  .home
    background-color: $bgColor
</style>
