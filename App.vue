<template>

  <div class="menu">
    <a v-for="amenu in menus" :key="amenu"> {{ amenu }} </a>
  </div>

  <div class="black_bg" v-if="infobox_open[0] == true">
    <div class="white_bg">
      <h4>Seoul</h4>
      <p>의 내용</p>
      <button @click="infobox_open[0] = false">close</button>

    </div>
  </div>





  <div>
    <img src="./assets/room0.jpg" class="room_img">
    <h4 @click="infobox_open[0] = true">{{oneroom_data[0].title}}</h4>
    <p>usd {{oneroom_data[0].price}}</p>
    <button @click="abuse_int[0]++">Report Abuse</button> <span>Int : {{abuse_int[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room_img">
    <h4>{{oneroom_data[1].title}}</h4>
    <p>usd {{oneroom_data[1].price}}</p>
    <button @click="abuse_int[1]++">Report Abuse</button> <span>Int : {{abuse_int[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room_img">
    <h4>{{products[2]}}</h4>
    <p>usd {{ price3 }}</p>
    <button @click="abuse_int[2]++">Report Abuse</button> <span>Int : {{abuse_int[2]}}</span>
  </div>
</template>

<script>

import oneroom_data from './assets/oneroom.js';
oneroom_data;

export default {
  name: 'App',
  data(){
    return{
      price1 : 60,
      price2 : 70,
      price3 : 80,
      products : ['seoul', 'goyang', 'busan' ],
      menus : ['Home', 'Products', 'About'],
      abuse_int : [0, 0, 0],
      infobox_open : [false, false],
      oneroom_data : oneroom_data,
    }
  },
  methods : {

  },
  components: {
    
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
}

.menu {
  background: rgb(30, 48, 151);
  padding: 15px;
  border-radius: 5px;

}

.menu a {
  color: white;
  padding: 10px;
}

.room_img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black_bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white_bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
