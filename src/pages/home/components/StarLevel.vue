<template>
  <ul class="starlevel">
		<li class="starlevel-item" v-for="i in nums" :key="i">
			<img class="starlevel-item-img" src="static/imgs/like/star.png">
		</li>
	</ul>
</template>

<script>
export default {
	name: 'StarLevel',
	props: {
		dataScore: Number
	},
	computed: {
		nums () {
			let temp = []
			let num = Math.ceil(this.dataScore)
			for(let i = 0; i < num; i++){
				temp.push(i)
			}
			return temp
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