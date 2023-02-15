<template>

  <div class="black-bg">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>



  <div class="menu">
    <a v-for = "(menu,i) in menus" :key="i">{{menu}}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">
  <div  v-for = "(product,i) in products" :key="i">
    <img v-bind:src="product.img" class = "room-img">
    <h4>{{product.name}}</h4>
    <p>{{product.price}} 만원</p>
    <button @click="product.report++">허위매물신고</button> <span>신고수 : {{product.report[i]}}</span>
  </div>

</template>

<script>


export default {
  name: 'App',
 data() {
    return {
      products: [
        {
          name: "역삼동 원룸",
          price: 60,
          report: 0,
          img: require("./assets/room0.jpg"),
        },
        {
          name: "천호동 원룸",
          price: 70,
          report: 0,
          img: require("./assets/room1.jpg"),
        },
        {
          name: "마포구 원룸",
          price: 100,
          report: 0,
          img: require("./assets/room2.jpg"),
        },
      ],
      menus: ["Home", "Products", "About"],
  }
 },
  methods: {
    //여기다가 함수 여러개 만들어놓으면됨
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
  margin-top: 60px;
}

.menu{
  background : darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

.room-img{
  width:100%;
  margin-top : 40px;
}

body{
  margin : 0 
}
div {
  box-sizing: border-box;
}
.black-bg{
  width :100%;
  height:100%;
  background: rgba(0,0,0,0.5);
  position:fixed;
  padding:20px;
}
.white-bg{
  width:100%;
  background:white;
  border-radius :8px;
  padding:20px;
}

</style>
