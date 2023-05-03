<template>
  <Transition name="fade">
    <DetailModal v-if="isDetail" @closeDetail="closeDetail" @openDetail="openDetail" :stores="stores"/>
  </Transition>
  <div class = 'menu'>
    <a v-for="{menu,i} in menus" :key="i">
    {{menu}}</a> 
  </div>
  <Discount />
  <!-- <div v-for ="(product,i) in products" :key= i>
    <img src="./assets/hongssam.jpg" class="ddeck-store" @click="openDetail">
    <h4> {{product}}</h4>
    <button @click="addRecomandCnt(i)" > 추천 </button>
    <span> 추천수 : {{recomandCnt[i]}} </span>
  </div> -->
  <StoreCard v-for="(store,i) in stores" :key="i" :store="stores[i]" :recomandCnt="recomandCnt[i]" @openDetail="openDetail"/>

</template>

<script>

import data from './assets/ddeckbockki.js';
import Discount from './DiscountBanner.vue';
import DetailModal from './DetailModal.vue';
import StoreCard from './StoreCard.vue';

export default {
  name: 'App',
  components: {
    Discount : Discount,
    DetailModal : DetailModal,
    StoreCard : StoreCard,
  },
  data() {
    return {
      stores : data,
      isDetail : false,
      menus : ['떡볶이', '기타'],
      products : ['하이','하이2'],
      recomandCnt : [0,0]
    }
  },
  methods : {
    addRecomandCnt(i){
      this.recomandCnt[i]++;
    },
    openDetail() {
      this.isDetail = true;
    },
    closeDetail() {
      this.isDetail = false;      
    }
  }
}
</script>

<style>
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: all 1s;
}
.fade-leave-to {
  opacity: 0;
}
body {
  margin:0;
}
div {
  box-sizing: border-box;
}
.ddeck-store {
  width: 200px;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu {
  background:  darkslateblue;
  padding : 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

</style>
