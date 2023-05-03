<template>
  <div class="black-bg">
    <div class="white-bg">
      <h4>{{stores[0].title}}</h4>
      <p>{{stores[0].content}}</p>
      <input v-model.number="month">
      <p>{{month}} 개월</p>
      <button @click="closeDetail">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailModal',
  props: {
    stores: Array,
  },
  data() {
    return {
      month: 0
    }
  },
  watch: {
    month(a,b){
      if(a > 13){
        alert('13이상')
      }
     console.log("## ab", a, b)
     console.log("##", isNaN(a))
      if(isNaN(a) == true) {
        console.log("## gd")
        
        this.month = 1;
      }
    }
  },
  methods: {
    closeDetail(){
       this.$emit('closeDetail');
    }
  }
}
</script>
<style>
.black-bg {
  width : 100%;
  height : 100%;
  background : rgba(0,0,0,0.5);
  position : fixed;
  padding : 20px;
}
.white-bg {
  width : 100%;
  background : white;
  border-radius : 8px;
  padding : 20px;
}
</style>