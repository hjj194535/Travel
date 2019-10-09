<template>
  <ul class="starlevel">
		<li class="starlevel-item" v-for="i in num" :key="i">
			<img class="starlevel-item-img" src="static/imgs/like/star.png">
		</li>
	</ul>
</template>

<script>
export default {
	name: 'StarLevel',
	props: ['dataScore'],
	data () {
		let nums = []
		let num = Math.ceil(this.dataScore)
		for(let i = 0; i < num; i++){
			nums.push(i)
		}
		return {
			num: nums
		}
	}
}
</script>

<style lang="stylus" scoped>
	.starlevel
		display: inline-block
		position: relative
		width: 1.5rem
		height: .28rem
		padding-left: 0
		.starlevel-item
			float: left
			overflow: hidden
			height: .28rem
			.starlevel-item-img
				height: .28rem
</style>