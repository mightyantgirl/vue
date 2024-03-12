<!-- html -->
<template>

  <div class="menu">
    <a v-for="i in menu" :key="i">{{i}}</a>
  </div>

  <!-- <div v-for="(a,i) in products" :key="i">
    <h4>{{products[i]}}</h4>
    <p>100만페소</p>
  </div> -->

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>파비앙과 로즈의 집</h4>
      <p>간혹 연주소리와 빵 굽는 냄새가 풍길 수 있어요!</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>

  <div class="room">
    <img class="room-img" src="./assets/room0.jpg">
    <h4 @click="modal = true">{{ products[0] }}</h4>
    <p>1박 {{ price[0] }}만 페소</p>
    <button v-on:click="increase(0)">추천하기</button> <span>추천 수 : {{ recommend[0] }}</span>
  </div>

  <div class="room">
    <img class="room-img" src="./assets/room1.jpg">
    <h4>{{ products[1] }}</h4>
    <p>1박 {{ price[1] }}만 페소</p>
    <button v-on:click="increase(1)">추천하기</button> <span>추천 수 : {{ recommend[1] }}</span>
  </div>

  <div class="room">
    <img class="room-img" src="./assets/room2.jpg">
    <h4>{{ products[2] }}</h4>
    <p>1박 {{ price[2] }}만 페소</p>
    <button v-on:click="increase(2)">추천하기</button> <span>추천 수 : {{ recommend[2] }}</span>
  </div>

</template>s


<!-- js -->
<script>

export default {
  name: 'App',
  
  data(){
    // 데이터보관함
    return {
      modal :  false,
      recommend : [0, 0, 0],
      menu : ["Home","Shop","About"],
      products : ["따뜻하고 포근한 파비앙과 로즈의 집🌹", "불러만 주세요! 5분 신속 메일보이의 집💌", "부에노스아이레스 우편국장 리비에르의 집📮"],
      price : ["5","3","10"]
    }
  },
  methods : {
    increase(i){
      this.recommend[i] += 1;
    }
  }
}
</script>


<!-- css -->
<style>
body{
  margin: 0;
}

div{
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background-color: #2c3e50;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: #fff;
  padding: 10px;
}

.room-img{
  width: 70%;
}

.room {
  margin: 0 0 40px;
}

.black-bg{
  width: 100%; height: 100%;
  background-color: #0000005a;
  position: fixed; padding: 20px;
}

.white-bg{
  width: 100%; 
  background: #ffffff;
  border-radius: 8px;  
  padding: 20px;
}
</style>
 