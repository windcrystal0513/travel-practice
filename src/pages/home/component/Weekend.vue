<template>
	<div>
		<div class="recommend-title">周末去哪儿</div>
		<ul>
			<li class="item border-bottom" v-for='item of recommendList' :key='item.id'>
				<div class="item-img-wrapper">
					<img  class="item-img" :src="item.imgUrl">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default{
	name:'HomeWeekend',
	data(){
		return{
			recommendList:[{
				id:'0001',
				imgUrl:'http://img1.qunarzz.com/sight/source/1505/74/98a840f2a881b.jpg_r_640x214_1bf94c8e.jpg',
				title:'陕西温泉季',
				desc:'养生、养性、养心的理想之地，曲径通幽，鸟语花香，让您在远离喧嚣之地享受终南隐士生活。'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/sight/source/1505/74/98a840f2a881b.jpg_r_640x214_1bf94c8e.jpg',
				title:'陕西温泉季',
				desc:'养生、养性、养心的理想之地，曲径通幽，鸟语花香，让您在远离喧嚣之地享受终南隐士生活。'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/sight/source/1505/74/98a840f2a881b.jpg_r_640x214_1bf94c8e.jpg',
				title:'陕西温泉季',
				desc:'养生、养性、养心的理想之地，曲径通幽，鸟语花香，让您在远离喧嚣之地享受终南隐士生活。'
			},{
				id:'0004',
				imgUrl:'http://img1.qunarzz.com/sight/source/1505/74/98a840f2a881b.jpg_r_640x214_1bf94c8e.jpg',
				title:'陕西温泉季',
				desc:'养生、养性、养心的理想之地，曲径通幽，鸟语花香，让您在远离喧嚣之地享受终南隐士生活。'
			},]
		}
	}
}	
</script>

<style lang='stylus' scoped>
	@import "~styles/mixins.styl"
	.recommend-title
		margin-top: .2rem
		line-height: .8rem
		background: #eee
		text-indent: .2rem
	.item-img-wrapper
		overflow:hidden
		height:0
		padding-bottom:33.9%
		.item-img
			width: 100%
	.item-info
		padding: .1rem
		.item-title
			ellipsis()
			line-height: .54rem
			font-size: .32rem
		.item-desc
			ellipsis()
			line-height: .4rem
			color: #ccc



</style>