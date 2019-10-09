<template>
    <div class="like">
        <div class="like-title">
				  <img src="static/imgs/like/title.png" class="title-img">
					<span>猜你喜欢</span>
				</div>
				<ul class="like-list">
					<li class="like-item" v-for="item in likeList" :key="item.id">
						<a href="#/" class="fulllink">
							<div class="like-imgcon">
								<img class="like-img" :src="item.imgUrl" :alt="item.name">
							</div>
							<div class="like-tag" 
								 style="background-image:url(static/imgs/like/icon-bg.png)">
								 随买随用
							</div>
							<div class="like-info">
								<div class="like-name">{{item.name}}</div>
								<div class="like-content">
									<star-level :dataScore="item.commentScore"></star-level>
									<span class="comment-num">{{item.commentNum}}条评论</span>
								</div>
								<div class="like-price">
									<span class="price">¥<em class="price-num">{{item.price}}</em></span>起
									<span class="like-address">{{item.address}}</span>
								</div>
							</div>
						</a>
					</li>
				</ul>
    </div>
	
</template>

<script>
import StarLevel from './StarLevel'
export default {
	name: 'Interested',
	components: {
		StarLevel
	},
	data () {
		return {
			likeList: [
				{
					id: '1001', 
					name: '兵马俑', 
					commentScore: 4.9, 
					commentNum: 163062,
					address: '临潼区',
					price: 100,
					imgUrl: 'static/imgs/hotRemmend/No_1.jpg'
				},
				{
					id: '1002', 
					name: '博物馆', 
					commentScore: 4.9, 
					commentNum: 163032,
					address: '碑林区',
					price: 0.5,
					imgUrl: 'static/imgs/hotRemmend/No_2.jpg'
				},
				{
					id: '1003', 
					name: '长恨歌', 
					commentScore: 4.9, 
					commentNum: 163082,
					address: '碑林区',
					price: 288,
					imgUrl: 'static/imgs/hotRemmend/No_3.jpg'
				},
				{
					id: '1004', 
					name: '华清池', 
					commentScore: 4.9, 
					commentNum: 163090,
					address: '临潼区',
					price: 100,
					imgUrl: 'static/imgs/hotRemmend/No_4.jpg'
				},
				{
					id: '1005', 
					name: '大唐芙蓉园', 
					commentScore: 4.9, 
					commentNum: 163062,
					address: '碑林区',
					price: 100,
					imgUrl: 'static/imgs/hotRemmend/No_5.jpg'
				},
				{
					id: '1006', 
					name: '西安钟楼', 
					commentScore: 4.9, 
					commentNum: 163162,
					address: '碑林区',
					price: 15,
					imgUrl: 'static/imgs/hotRemmend/No_6.jpg'
				},
				{
					id: '1007', 
					name: '大明宫国家遗址公园', 
					commentScore: 4.9, 
					commentNum: 163062,
					address: '未央区',
					price: 82,
					imgUrl: 'static/imgs/hotRemmend/No_7.jpg'
				}

			]
		}
	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins'
@import '~styles/varibles.styl'
.like 
	margin-top: .2rem
	background: #fff
	.like-title
		indexTitle()
		.title-img
			indexTitleImg()
	.like-list
		padding: 0
		magin: 0
		margin-left: .24rem
		.like-item
			position: relative
			overflow: hidden
			padding: .24rem 0
			.fulllink
				display: block
				width: 100%
				height: 100%
				cursor: crosshair
			.like-imgcon
				float: left
				overflow: hidden
				width: 2rem
				height: 2rem
				background: #f0f5f8
				.like-img
					width: 100%
					height: auto
			.like-tag
				position: absolute 
				top: .2rem
				left: 0
				width: 1.02rem
				height: .38rem
				baground-size: 100%
				color: #ffffff
				font-size: .2rem
				line-height: .38rem
				text-indent: .04rem
			.like-info
				overflow: hidden
				padding-left: .22rem
				.like-name
					margin-top: .26rem
					height: .44rem
					color: #212121
					font-size: .32rem
					line-height: .44rem
					ellipsis()
				.like-content
					margin-top: .14rem
					height: .34rem
					.comment-num
						color: $aTextColor
						font-size: .24rem
						line-height: .34rem
						vertical-align: text-bottom
				.like-price
					position: relative
					margin-top: .22rem
					color: $aTextColor
					font-size: .24rem
					line-height: .4rem
					.price
						color: $priceColor
						.price-num
							font-size: .4rem
					.like-address
						position: absolute 
						right: .24rem
						bottom: 0

							




					

								

						






			

	

</style>
