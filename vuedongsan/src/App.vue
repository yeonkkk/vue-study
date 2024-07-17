<template>

<div class="black-bg" v-if="modal_open">
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    <button @click="modal_open=false">닫기</button>
  </div>
</div>

  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>

  <div v-for="(a, i) in 6" :key="a">
    <img :src="rooms[i].image" class="room-img">
    <h4> {{rooms[i].title}} </h4>
    <p> {{rooms[i].price}} 원 </p>
  </div>
  
</template>

<script>

import data from './assets/data.js';

export default {
  name: 'App',
  // 데이터 보관함
  data(){
    return {
      rooms: data,
      modal_open: false,
      prices : [60, 70, 80],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus : ['Home', 'Shop', 'About'],
      counts : [0, 0, 0]
    }
  },
  methods: {
    increase(i) {
      this.counts[i] += 1;
    }
  },
  components: {
    
  }
}
</script>

<style>
body {
  margin : 0
}
div {
  box-sizing : border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

</style>
