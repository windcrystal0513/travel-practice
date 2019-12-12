<template>
	<div>
		<detail-banner :sightName='sightName' :bannerImg='bannerImg' :gallaryImgs='gallaryImgs'></detail-banner>
		<detail-header></detail-header>
		<div class="content">
			<detail-list :list='list'></detail-list>
		</div>

	</div>
</template>

<script>
import DetailBanner from './component/Banner.vue'
import DetailHeader from './component/Header.vue'
import DetailList from './component/List.vue'
import axios from 'axios'
export default{
	name:'Detail',
	components:{
		DetailBanner,
		DetailHeader,
		DetailList
	},
	data () {
		return {
			sightName:'',
			bannerImg:'',
			gallaryImgs:[],
			list:[]
		}
	},
	methods:{
		getDetailInfo () {
			axios.get('/static/mock/detail.json?id='+this.$route.params.id)
			.then(this.handleGetDataSucc)
		},
		handleGetDataSucc(res) {
			res=res.data
			if (res.ret&&res.data) {
				this.sightName=res.data.sightName
				this.bannerImg=res.data.bannerImg
				this.gallaryImgs=res.data.gallaryImgs
				this.list=res.data.categoryList
			}
		}
	},
	mounted() {
		this.getDetailInfo()
	}
}
</script>

<style lang='stylus' scoped>
	.content
		height:50rem
</style>