<template>
    <div>
			<div class="search">
				<input v-model="keyWord" class="search-input" 
				type="text" placeholder="输入城市名或拼音">
			</div>
			<div class="search-content" ref="search" v-show="keyWord">
				<ul class="">
					<li class="search-item border-bottom" 
					v-for="item of list" :key="item.id">{{item.name}}</li>
					<li class="search-item border-bottom" v-show="showNoData">没有找到匹配数据</li>
				</ul>
			</div>
		</div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
	name: 'CitySearch',
	props: {
		cities: Object
	},
	data () {
		return {
			keyWord: '',
			list: [],
			timer: null
		}
	},
	watch: {
		keyWord () {
			if (this.timer) {
				clearTimeout(this.timer)
			}
			if (!this.keyWord) {
				this.list = []
				return
			}
			this.timer = setTimeout(() => {
				const result = []
				for (let i in this.cities) {
					this.cities[i].forEach((value) => {
						if (value.spell.indexOf(this.keyWord) > -1 || 
						value.name.indexOf(this.keyWord) > -1){
							result.push(value)
						}
					})
				}
				this.list = result
			}, 100)
			
		}
	},
	mounted () {
		this.scroll = new Bscroll(this.$refs.search)
	},
	computed: {
		showNoData () {
			return !this.list.length
		}
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles'
	.search
		height: .72rem
		padding: 0 .1rem
		background: $headerColor
		text-align: center
		.search-input
			box-sizing: border-box
			height: .62rem
			padding: 0 .1rem
			line-height: .62rem
			width: 100%
			text-align: center
			color: #666
	.search-content
		z-index: 1
		position: absolute
		top: 1.58rem
		left: 0
		right: 0
		bottom: 0
		background: #eee
		.search-item
			line-height: .62rem
			padding-left: .2rem
			background: $white
			color: #666


</style>