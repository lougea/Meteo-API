
<template>
<div class="cityDiv">

  <img id="logo" src="../assets/logo1.png" alt="">
  <br>
  <input class="city1" type="text" v-model="city" placeholder="Search" @keyup.enter="api(city)">
  <h1>{{city}}</h1>
  <p>{{pressure}}</p>
  <p>{{humidity}}</p>
  <img :src="icon" alt="">




</div>
</template>

<script>
import {TweenMax, Power2, TimelineLite} from "gsap/TweenMax"
export default {
  name: 'barre',
  data() {
    return {
      city: "",
      apiTable: [{
        currentTemp: '',
        minTemp: '',
        maxTemp: '',
        sunrise: '',
        sunset: '',
        pressure: '',
        humidity: '',
        wind: '',
        overcast: '',
        icon: '',
      }]
    }
  },
  methods: {
    api(city) {
      var link = "https://api.openweathermap.org/data/2.5/weather?q=" + city + "&units=metric&APPID=b5adeb2fa879be2ce6147b10c08e02c5";
      this.axios.get(link).then((response) => {
        console.log(response.data)
        // console.log(response.data.weather);
        // console.log(response.data.main);
        this.currentTemp = response.data.main.temp;
        this.minTemp = response.data.main.temp_min;
        this.maxTemp = response.data.main.temp_max;
        this.pressure = response.data.main.pressure;
        this.humidity = response.data.main.humidity + '%';
        this.wind = response.data.wind.speed + 'm/s';
        this.overcast = response.data.weather[0].description;
        this.icon = "http://openweathermap.org/img/w/" + response.data.weather[0].icon + ".png";
      })
    },
    mounted() {

        var box  = document.getElementById('logo')
        TimelineLite.to(box, 1, { x: 200, rotation: 90 })
      },
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img{

}

h1 {
  color: black;
}

.cityDiv {
  top: 0;
  height: 1000px;
  width: 100%;
  background-image: url('../assets/nuage.jpg');
  background-size: cover
}

.city1 {
  margin: 40px;
}

#logo {
  margin-top: 60px;
}


button {
  background-image: url('../assets/loupe.svg');
}
</style>
