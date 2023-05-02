<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class = 'menu'>
    <a v-for="{menu,i} in menus" :key="i">
    {{menu}}</a> 
  </div>
  <div>
    <h4> {{products[0]}}</h4>
    <button @click="recomandCnt++"> 추천 </button>
    <span> 추천수 : {{recomandCnt}} </span>
  </div>
  <div>
    <h4> {{products[1]}}</h4>

  </div>
  <div v-for ="product in products" :key= product>
    <h4> {{product}}</h4>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      menus : ['떡볶이', '기타'],
      products : ['하이','하이2'],
      recomandCnt : 0
    }
  }
}
</script>

<style>
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
