<template>
<div>
	<city-header></city-header>
	<city-search :cities='cities'></city-search>
	<city-list :cities='cities' :hot='hotCities' :letter='letter'></city-list>
	<city-alphabet :cities='cities' @change='handleLetterChange'></city-alphabet>
</div>
</template>

<script>
import CityHeader from './component/Header.vue'
import CitySearch from './component/Search.vue'
import CityList from './component/List.vue'
import CityAlphabet from './component/Alphabet.vue'
import axios from 'axios'
export default {
	name:'City',
	data(){
		return{
			cities:{},
			hotCities:[],
			letter:''
		}
	},
	components:{
		CityHeader,
		CitySearch,
		CityList,
		CityAlphabet
	},
	methods:{
			getCityInfo(){
				axios.get('/static/mock/city.json')
				.then(this.getCityInfoSucc)
			},
			getCityInfoSucc(res){
				console.log('1')
				res=res.data
				// console.log(res)
				if(res.ret&&res.data){
					this.cities=res.data.cities
					this.hotCities=res.data.hotCities
				}
			},
			handleLetterChange(letter){
				this.letter=letter
			}
		},
		mounted(){
			this.getCityInfo()
		}
}
</script>

<style lang='stylus' scoped>
	
</style>