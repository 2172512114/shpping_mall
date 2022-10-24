<template>
  <div class="Recommend">
    <div class="Recommend-item" v-for="(item,index) in recommend" :key="index">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <p class="title">{{ item.title }}</p>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RecommendView',
  props:{
    recommend:{
      type: Array,
      default(){
        return []
      }
    }
  }
}
</script>

<style scoped>
.Recommend{
  display: flex;
  text-align: center;
  line-height: 20px;
  padding: 20px 0 30px 0;
  border-bottom: 8px solid #eee;
}
.Recommend-item{
  flex: 1;
  width: 25%;
  margin:0 10px 0 10px;
}
.Recommend-item img{
  width: 100%;
}
.title{
  font-size: 14px;
  color: #000;
}
</style>