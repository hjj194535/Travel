<template>
    <div class="weekend-trip">
        <h2 class="weeknd-title">周末去哪儿</h2>
				<div>
					<div class="product-item" v-for="item in weekendTripList" :key="item.id">
						<a href="" :title="item.name" class="fulllink">
							<div class="product-img">
								<img :src="item.imgUrl" :alt="item.id">
							</div>
							<div class="product-info">
								<p class="product-name">{{item.name}}</p>
								<p class="product-desc">{{item.desc}}</p>
							</div>
						</a>
					</div>
				</div>
				
    </div>
		
</template>

<script>
export default {
		name: 'Weekend',
		data () {
			return {
				weekendTripList:[
					{
						id: '1001',
						name: '西安必打卡',
						desc: '寻长安梦，开启穿越的圆梦之旅',
						imgUrl: 'static/imgs/weekend/zhonglou.jpg'
					},
					{
						id: '1002',
						name: '探寻文化古都',
						desc: '一场时空穿越的旅行，探寻历史悠久的文化古都！寻觅历史留下的点点足迹，细细品味古人的伟大',
						imgUrl: 'static/imgs/weekend/bingmayong.jpg'
					},
					{
						id: '1003',
						name: '西安演出在线',
						desc: '寻长安梦，开启穿越的圆梦之旅这里有绚丽奇幻的神秘梦幻舞剧，歌舞揭开盛唐面纱，体验穿越时空的奇妙，感受大唐之盛世',
						imgUrl: 'static/imgs/weekend/yanchu.jpg'
					},
					{
						id: '1004',
						name: '西安亲子必玩',
						desc: '西安亲子必去景点，和家人一起度过欢乐亲子时光，带你嗨翻假期！',
						imgUrl: 'static/imgs/weekend/lehuacheng.jpg'
					},
					{
						id: '1005',
						name: '醉美丝路行',
						desc: '情系西北，中国梦丝路行',
						imgUrl: 'static/imgs/weekend/sichouzhilu.jpg'
					}
				]
			}
		}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles'
.product-item,.product-info
	padding: .14rem .2rem .2rem .2rem
.product-item,.product-name,.product-desc
	overflow: hidden
	padding-right: 1.4rem
	color: $darkTextColor
	font-size: .28rem
	line-height: .48rem
	white-space: nowrap
	text-overflow: ellipsis
.weeknd-title
	height: .8rem
	padding-left: .26rem
	line-height: .8rem
	color: $darkTextColor
.product-item
	position: relative
	margin-bottom: .1rem
	background: #ffffff
	.fulllink
		display: block
		width: 100%
		height: 100%
		.product-img
			overflow: hidden
			height: 0
			padding-bottom: 37.4375%
</style>