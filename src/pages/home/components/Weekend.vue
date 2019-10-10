<template>
    <div class="weekend-trip">
        <h2 class="weeknd-title">周末去哪儿</h2>
				<div>
					<div class="product-item" v-for="item in this.weekendTripList" :key="item.id">
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
		props: {
			weekendTripList: Array
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