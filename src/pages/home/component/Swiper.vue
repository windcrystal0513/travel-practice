<template>
<div class="wrapper">
	<swiper :options="swiperOption">
	    <!-- slides -->
	    <swiper-slide v-for='item of swiperList' :key='item.id'>
	    	<img  class="swiper-img" :src="item.imgUrl" >
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>	
 </div>
</template>

<script>
export default{
	name:'HomeSwiper',
	data() {
		return{
			swiperOption:{
				pagination:'.swiper-pagination', 
				autoplay:2000,     
				loop:true
			},
			swiperList:[{
				id:'0001',
				imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201912/9accc56ec000de669ce90d0b3f44af86.jpg_750x200_b35b86a0.jpg'
			},{
				id:'0002',
				imgUrl:"http://img1.qunarzz.com/piao/fusion/1609/47/0cfdc871ac183702.jpg_750x200_f6896acd.jpg"
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/piao/fusion/1805/fe/ca8ed7adc3ff9f02.jpg_750x200_49735140.jpg'
			}]
		}
	}
}
</script>

<style lang='stylus' scoped>
	.wrapper>>>.swiper-pagination-bullet-active
		background:white
	.wrapper
		width:100%
		height:0
		overflow:hidden
		padding-bottom:31.25%
		.swiper-img
			width:100%
</style>