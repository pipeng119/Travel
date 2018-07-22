<template>
	<div>
		<home-header :city="city"></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>
	</div>
</template>
<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  data(){
	  return {
		  city: '',
		  swiperList: [],
		  iconList: [],
		  recommendList: [],
		  weekendList: [],
	  }
  },
  components: {
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecommend,
		HomeWeekend,
  },
  methods: {
	  getHomeInfo(){
		  const that = this
		  axios.get('/api/index.json')
		  	.then( res => {
				if(res){
					const data = res.data
					if(data.ret){
						that.swiperList = data.data.swiperList
						that.iconList = data.data.iconList
						that.recommendList = data.data.recommendList
						that.weekendList = data.data.weekendList
					}
				}
			})
			.catch( err => {

			})
	  }
  },
  mounted(){
	  this.getHomeInfo()
  }
}
</script>
<style>

</style>
