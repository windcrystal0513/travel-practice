<template>
	<div class='icons'>
		<swiper :options="swiperOption">
			<swiper-slide v-for='(page,index) of pages' :key='index'>
				<div class="icon" v-for='item of page' :key='item.id'>
					<div class="icon-img"><img  class="icon-img-content" :src="item.imgUrl"></div>
					<p class="icon-desc">{{item.textContent}}</p>
				</div>
			</swiper-slide>
			<div class="swiper-pagination"  slot="pagination"></div>
		</swiper>
	</div>
</template>

<script>
export default{
	name:'HomeIcons',
	data(){
		return{
			swiperOption:{
				pagination:'.swiper-pagination', 
				autoplay:2000,     
				loop:true
			},

			iconList:[{
						id:'0001',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
						textContent:'热门景点'
					},{
						id:'0002',
						imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/f0f00d6dfe038c044dbc9a437f58b0eb.png',
						textContent:'一日行'
					},{
						id:'0003',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
						textContent:'芙蓉园'
					},{
						id:'0004',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
						textContent:'泡温泉'
					},{
						id:'0005',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
						textContent:'一日游'
					},{
						id:'0006',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
						textContent:'动植物园'
					},{
						id:'0007',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
						textContent:'华清宫'
					},{
						id:'0008',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
						textContent:'兵马俑'
					},{
						id:'0009',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
						textContent:'大明宫'
					}]
		}
	},
	computed:{
		pages () {
			const pages=[]
			this.iconList.forEach((item,index)=>{
				const page=Math.floor(index/8)
				if(!pages[page]){
					pages[page]=[]
				}
				pages[page].push(item)
			})
			return pages

		}
	}
}
</script>

<style lang='stylus' scoped>
	@import "~styles/varibles.styl"
	@import "~styles/mixins.styl"
	.icons>>>.swiper-pagination-bullet-active
		background:$bgColor
		margin-bottom:-.2rem
	.icons>>>.swiper-pagination-bullet
		margin-bottom:-.2rem
	.icons>>>.swiper-container
		height:0
		padding-bottom:50%
	.icon
		position:relative
		overflow:hidden
		float:left
		height:0
		width:24%
		padding-bottom:24%
		
		.icon-img
			position:absolute
			top:0
			left:0
			right:0
			bottom:.44rem
			box-sizing:border-box
			padding: .1rem
			
			.icon-img-content
				display:block
				height:100%
				margin:0 auto
		.icon-desc
			position:absolute
			left:0
			right:0
			bottom:0
			height: .44rem
			line-height: .44rem
			text-align:center
			color:$darkTextColor
			ellipsis()	
		


</style>