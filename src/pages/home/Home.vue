<template>
<div>
	<home-header ></home-header>
	<home-swiper :list='swiperList'></home-swiper>
	<home-icons :list='iconList'></home-icons>
	<home-recommend :list='recommendList'></home-recommend>
	<home-weekend :list='weekendList'></home-weekend>
</div>
</template>

<script>
import HomeHeader from './component/Header.vue'
import HomeSwiper from './component/Swiper.vue'
import HomeIcons from './component/Icons.vue'
import HomeRecommend from './component/Recommend.vue'
import HomeWeekend from './component/Weekend.vue'
import axios from 'axios'
import {mapState} from 'vuex'
export default{
		name:'Home',
		data(){
			return {
				lastCity:' ',
				swiperList:[],
				iconList:[],
				recommendList:[],
				weekendList:[]
			}
		},
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend,
			HomeWeekend
		},
		computed:{
			...mapState(['city'])
		},
		methods:{
			getHomeInfo(){
				axios.get('/static/mock/index.json?city='+this.city)
				.then(this.getHomeInfoSucc)
			},
			getHomeInfoSucc(res){
				res=res.data
				console.log(res)
				if(res.ret&&res.data){
					this.swiperList=res.data.swiperList
					this.iconList=res.data.iconList
					this.recommendList=res.data.recommendList
					this.weekendList=res.data.weekendList

				}
			}
		},
		mounted(){
			this.lastCity=this.city
			this.getHomeInfo()
		},
		activated() {
			if (this.lastCity!==this.city){
				this.lastCity=this.city
				this.getHomeInfo()
			}
		}
}
</script>

<style>
	
</style>