<template>
<div>
	<home-header></home-header>
	<home-swiper></home-swiper>
	<home-icons></home-icons>
	<home-recommend></home-recommend>
</div>
</template>

<script>
import HomeHeader from './component/Header.vue'
import HomeSwiper from './component/Swiper.vue'
import HomeIcons from './component/Icons.vue'
import HomeRecommend from './component/Recommend.vue'
export default{
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend
		}
}
</script>

<style>
	
</style>