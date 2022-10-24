<template>
  <div>
    <nav-bar class="home-nav">
      <p slot="center">购物街</p>
    </nav-bar>
    <home-swiper :banners="bannerImg" />
    <recommend-view :recommend="recommend" />
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar';
import HomeSwiper from './childComps/HomeSwiper.vue';
import RecommendView from './childComps/RecommendView.vue';

import { getHomeMultidata } from 'network/home';
export default {
  name: 'Home',
  components:{
    NavBar,
    HomeSwiper,
    RecommendView
  },
  data(){
    return{
      bannerImg:[],
      recommend:[],
      dKeyword:[],
      keywords:[]
    }
  },
  methods:{
    initData(){
      getHomeMultidata().then(res => {
        console.log(res.data.recommend.list);
        if(res.success){
          this.bannerImg = res.data.banner.list
          this.recommend = res.data.recommend.list
          this.dKeyword = res.data.dKeyword.list
          this.keywords = res.data.keywords.list
        }else{
          alert('请求失败')
        }
      }).catch(err => {
        console.log(err);
      })
    }
  },
  created(){
    this.initData()
  }
}
</script>

<style scoped>
.home-nav{
  background: var(--color-tint);
  color: #fff;
}
</style>