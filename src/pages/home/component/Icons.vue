<template>
	<div class='icons'>
		<swiper :options="swiperOption" v-if='showSwiper'>
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
	props:{
		list:Array
	},
	data(){
		return{
			swiperOption:{
				pagination:'.swiper-pagination',   
				loop:true
			}
		}
	},
	computed:{
		pages () {
			const pages=[]
			this.list.forEach((item,index)=>{
				const page=Math.floor(index/8)
				if(!pages[page]){
					pages[page]=[]
				}
				pages[page].push(item)
			})
			return pages

		},
		showSwiper(){
			return this.list.length
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