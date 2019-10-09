<template>
	<div class="hot">
		<div class="hot-list">
      <div class="hot-list-title">
				<img class="title-img" src="static/imgs/hotRemmend/title_icon.png">
				<span class="title-content">本周热门榜单</span>
				<a class="title-more" href="#/">全部榜单&gt;</a>
      </div>
			<div class="hot-list-content">
				<ul class="hot-list-ul">
					<li class="hot-list-item" v-for="item of hotList" :key="item.id">
						<a href="#/" class="hot-list-link">
							<div class="hot-list-tag">
								<img :src="item.imgUrl" :alt="item.desc" class="hot-list-tagimg">
								<div class="hot-list-desc">{{item.desc}}</div>
								<div class="hot-list-price">
									<span>¥<em class="price">{{item.price}}</em></span>起
								</div>
							</div>
						</a>
					</li>
				</ul>
			</div>
    </div>
	</div>
</template>

<script>
export default {
	name: 'HotList',
	data () {
		return {
			hotList: [
				{id: '001', imgUrl: 'static/imgs/hotRemmend/No_1.jpg',desc: '秦始皇陵博物院（兵马俑）',price: 100},
				{id: '002', imgUrl: 'static/imgs/hotRemmend/No_2.jpg',desc: '陕西历史博物馆',price: 0.5},
				{id: '003', imgUrl: 'static/imgs/hotRemmend/No_3.jpg',desc: '长恨歌',price: 288},
				{id: '004', imgUrl: 'static/imgs/hotRemmend/No_4.jpg',desc: '华清宫',price: 100},
				{id: '005', imgUrl: 'static/imgs/hotRemmend/No_5.jpg',desc: '大唐芙蓉园',price: 100},
				{id: '006', imgUrl: 'static/imgs/hotRemmend/No_6.jpg',desc: '西安钟楼',price: 15},
				{id: '007', imgUrl: 'static/imgs/hotRemmend/No_7.jpg',desc: '大明宫国家遗址公园',price: 82}
			]
		}
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	@import '~styles/mixins'
	.hot
		overflow: hidden
		// height: 0
		// padding-bottom: 40%
		margin-top: .2rem

		.hot-list
			position: relative
			background: $white

			.hot-list-title
				indexTitle()

				.title-img
					indexTitleImg()

				.title-content
					indexTitleContent()

				.title-more
					position: absolute
					top: .36rem
					right: .32rem
					color: $aTextColor
					font-size: .24rem
					line-height: .28rem

			.hot-list-content
				overflow: hidden
				width: 100%
				// height: 0
				// padding-bottom: 90%
				position: relative

				.hot-list-ul
					padding: 0 .24rem
					overflow-x: scroll
					white-space: nowrap
					

					.hot-list-item
						position: relative
						display: inline-block
						padding: .06rem .06rem .2rem
						width: 2rem

						.hot-list-link
							display: block
							width: 100%
							height: 100%

							.hot-list-tag
								overflow: hidden
								width: 2rem
								height: 100%
								background: #f0f5f8
								padding-bottom: .24rem

								.hot-list-tagimg
									width: 100%
									height: auto
								
								.hot-list-desc
									margin-top: .12rem
									color: #212121
									font-size: .24rem
									line-height: .32rem
									text-align: center
									ellipsis()

								.hot-list-price
									color: #616161
									font-siz: .24rem
									line-height: .32rem
									text-align: center
									.price
										color: #ff8300

								



								
									

</style>

