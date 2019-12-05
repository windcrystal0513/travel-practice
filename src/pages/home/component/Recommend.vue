<template>
	<div>
		<div class="recommend-title">热销推荐</div>
		<ul>
			<li class="item border-bottom" v-for='item of recommendList' :key='item.id'>
				<img  class="item-img" :src="item.imgUrl">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default{
	name:'HomeRecommend',
	data(){
		return{
			recommendList:[{
				id:'0001',
				imgUrl:'http://img1.qunarzz.com/sight/p0/201403/10/b0e7eeb18db9a7dc4f0376a13d4ab15d.jpg_200x200_3ff00ade.jpg',
				title:'西安关中民俗艺术博物馆',
				desc:'西安关中民俗页数博物馆介绍'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/sight/p0/201403/10/b0e7eeb18db9a7dc4f0376a13d4ab15d.jpg_200x200_3ff00ade.jpg',
				title:'西安关中民俗艺术博物馆',
				desc:'西安关中民俗页数博物馆介绍'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/sight/p0/201403/10/b0e7eeb18db9a7dc4f0376a13d4ab15d.jpg_200x200_3ff00ade.jpg',
				title:'西安关中民俗艺术博物馆',
				desc:'西安关中民俗页数博物馆介绍'
			},{
				id:'0004',
				imgUrl:'http://img1.qunarzz.com/sight/p0/201403/10/b0e7eeb18db9a7dc4f0376a13d4ab15d.jpg_200x200_3ff00ade.jpg',
				title:'西安关中民俗艺术博物馆',
				desc:'西安关中民俗页数博物馆介绍'
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
	.item
		display:flex
		height: 1.9rem
		overflow:hidden
		.item-img
			width: 1.7rem
			height:1.7rem
			padding: .1rem
		.item-info
			min-width:0
			flex:1
			padding: .1rem
			.item-title
				ellipsis()
				line-height: .54rem
				font-size: .32rem
			.item-desc
				ellipsis()
				line-height: .4rem
				color: #ccc
			.item-button
				line-height: .44rem
				background:#ff9300
				padding: 0 .2rem
				border-radius: .06rem
				margin-top: .16rem
				color:#fff



</style>