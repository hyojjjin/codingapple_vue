<template>
  <div>
    <img :src="store.image" class="ddeck-store" @click="openDetail">
    <h4> {{store.title}}</h4>
    <button @click="addRecomandCnt(i)" > 추천 </button>
    <span> 추천수 : {{recomandCnt}} </span>
  </div> 
</template>

<script>
export default {
  name: 'StoreCard',
  props: {
    store: Object,
    recomandCnt: Number,
  },
  methods: {
    openDetail() {
      this.$emit('openDetail');
    }
  },
}
</script>
<style>
</style>