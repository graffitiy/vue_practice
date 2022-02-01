<template>

  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>

  <div class="black-bg" v-if=" modal === true">
    <div class="white-bg">
      <h4>Detail Page</h4>
      <button @click="modal = false">close</button>
    </div>
  </div>

  <button @click="modal = true">Open Modal</button>
 
  <div v-for="i in 5" :key="i">
      <img :src ="onerooms[i].image">
    <h4>{{ onerooms[i].title }}</h4>
    <p>{{ onerooms[i].price }}</p>
  </div>
</template>

<script>  

import data from "./oneroom";

export default {
  name: 'App',
  data(){
    return {
        onerooms: data,
        modal : false,
        counts : [0, 0, 0], 
        menus: ['Home', 'Shop', 'About'],
        products : ['역삼동원룸', '천호동원룸', '마포구원룸'], 
      }
  },

  methods : {
 
  },

  components: {
  }
}
</script>

<style>

body{
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; 
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;  
  background: white;
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
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
