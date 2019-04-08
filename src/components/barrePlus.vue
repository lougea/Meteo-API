
<template>
<div class="cityDiv">
  <img id="logo" src="https://raw.githubusercontent.com/lougea/API-meteo/master/dev/src/assets/logo1.png" alt="">
  <br>
  <input class="city1" type="text" v-model="city" placeholder="Enter a city" @keyup.enter="api(city)">
  <br>
  <div class="container box1">
    <div class="row">
      <div class="col-md-4 "></div>
      <div class="col-md-4">
        <h1>{{cityy}}</h1>
        <h3>{{ date | moment("dddd do MMMM YYYY") }}</h3>
        <h2>{{currentTemp}}</h2>
      </div>
      <div class="col-md-4"></div>
    </div>

    <div class="row">
      <div class="col-md-4 extremiteL">
        <h4> {{minTemp}} </h4>
      </div>
      <div class="col-md-4">
        <img :src="icon" alt="" width="50%">
          <h4> {{overcast}} </h4>
      </div>
      <div class="col-md-4 extremiteR">
        <h4> {{maxTemp}} </h4>
      </div>
    </div>


    <div class="row secondaire">
      <div class="col-md-4 extremiteL">
        <h4 class="grey"> {{wind}} </h4>
      </div>
      <div class="col-md-4"></div>
      <div class="col-md-4 extremiteR">
        <h4 class="grey"> {{humidity}} </h4>
      </div>
    </div>
  </div>

<br>
<br>
<!-- " afficheDiv == false ? { 'display': 'none' } : { 'display': 'flex'}" -->
  <div class="dayDiv" >
     <div class="container box2">
   <!--******************************* Aujourd'hui +1 ********************************-->
      <div class="row">

        <div class="col-md-2 offset-2 indi">

          <div class="row">
            <div class="col-md-3 "></div>
            <div class="col-md-6">
            <h4>{{ date1 | moment("ddd") }}</h4>
            </div>
            <div class="col-md-3"></div>
          </div>

          <div class="row">
            <div class="col-md-4 extremiteDayMin">
               {{minTemp1}}
            </div>
            <div class="col-md-4">
              <img :src="icon" alt="">
            </div>
            <div class="col-md-4 extremiteDayMax">
              {{maxTemp1}}
            </div>
          </div>

          <div class="row">
            <div class="col-md-3"> </div>
            <div class="col-md-6">
            <h3>{{currentTemp1}}</h3>
            </div>
            <div class="col-md-3"> </div>
          </div>

      </div>
         <!--******************************* Aujourd'hui +2 ********************************-->
        <div class="col-md-2 indi">
          <div class="row">
            <div class="col-md-3 "></div>
            <div class="col-md-6">
            <h4>{{ date2 | moment("ddd") }}</h4>
            </div>
            <div class="col-md-3"></div>
          </div>

          <div class="row">
            <div class="col-md-4 extremiteDayMin">
               {{minTemp2}}
            </div>
            <div class="col-md-4">
              <img :src="icon" alt="">
            </div>
            <div class="col-md-4 extremiteDayMax">
              {{maxTemp2}}
            </div>
          </div>

          <div class="row">
            <div class="col-md-3"> </div>
            <div class="col-md-6">
            <h3>{{currentTemp2}}</h3>
            </div>
            <div class="col-md-3"> </div>
          </div>
        </div>
         <!--******************************* Aujourd'hui +3 ********************************-->
        <div class="col-md-2 indi">
          <div class="row">
            <div class="col-md-3 "></div>
            <div class="col-md-6">
            <h4>{{ date3 | moment("ddd ") }}</h4>
            </div>
            <div class="col-md-3"></div>
          </div>

          <div class="row">
            <div class="col-md-4 extremiteDayMin">
               {{minTemp3}}
            </div>
            <div class="col-md-4">
              <img :src="icon" alt="">
            </div>
            <div class="col-md-4 extremiteDayMax">
              {{maxTemp3}}
            </div>
          </div>

          <div class="row">
            <div class="col-md-3"> </div>
            <div class="col-md-6">
            <h3>{{currentTemp3}}</h3>
            </div>
            <div class="col-md-3"> </div>
          </div>
        </div>
         <!--******************************* Aujourd'hui +4 ********************************-->
        <div class="col-md-2 indi">
          <div class="row">
          <div class="col-md-3 "></div>
          <div class="col-md-6">
          <h4>{{ date4 | moment("ddd") }}</h4>
          </div>
          <div class="col-md-3"></div>
        </div>

        <div class="row">
          <div class="col-md-4 extremiteDayMin">
             {{minTemp4}}
          </div>
          <div class="col-md-4">
            <img :src="icon" alt="">
          </div>
          <div class="col-md-4 extremiteDayMax">
            {{maxTemp4}}
          </div>
        </div>

        <div class="row">
          <div class="col-md-3"> </div>
          <div class="col-md-6">
          <h3>{{currentTemp4}}</h3>
          </div>
          <div class="col-md-3"> </div>
        </div></div>

      </div>
    </div>

  </div>

</div>


</template>

<script>
import {TweenMax} from "gsap"
export default {
  name: 'barrePlus',
  data() {
    return {
      city:"",
      date1:"",
      afficheDiv: false,
      tableInfo:[{
        date :String,
        cityy : String,
        currentTemp :"",
        minTemp :"",
        maxTemp :"",
        pressure:"",
        humidity:"",
        wind :"",
        overcast:"",
        icon:"",

        date:"",
        cityy : "",
        currentTemp :"",
        minTemp :"",
        maxTemp :"",
        pressure:"",
        humidity:"",
        wind :"",
        overcast:"",
        icon:"",

        date :"",
        cityy : "",
        currentTemp :"",
        minTemp :"",
        maxTemp :"",
        pressure:"",
        humidity:"",
        wind :"",
        overcast:"",
        icon:"",

        date1 :"",
        currentTemp1 :"",
        minTemp1 :"",
        maxTemp1 :"",
        icon1:"",

        date2 :"",
        currentTemp2 :"",
        minTemp2 :"",
        maxTemp2 :"",
        icon2:"",

        date3 :"",
        currentTemp3 :"",
        minTemp3 :"",
        maxTemp3 :"",
        icon3:"",

        date4 :"",
        currentTemp4 :"",
        minTemp4 :"",
        maxTemp4 :"",
        icon4:"",
      }]
    }
  },
  methods: {
//
// formatDate: function(value){
//   return moment(string(value)).format(MM/DD/YYYY)
//

    api(city) {

      var link = "https://api.openweathermap.org/data/2.5/forecast?q="+city+"&units=metric&APPID=b5adeb2fa879be2ce6147b10c08e02c5";

      console.log(link)

      document.getElementsByClassName('dayDiv')[0].setAttribute("style","display : flex");

      this.axios
      .get(link)
      .then((response) => {
          console.log(response.data);
          // AUJOURD'HUI
          this.date = response.data.list[0].dt_txt;
          this.cityy = response.data.city.name;
          this.currentTemp = response.data.list[0].main.temp + "°";
          this.minTemp = "Min: " + response.data.list[0].main.temp_min + "°";
          this.maxTemp = "Max: " + response.data.list[0].main.temp_max + "°";
          this.pressure = response.data.list[0].main.pressure;
          this.humidity = "Humidity: "+ response.data.list[0].main.humidity + '%';
          this.wind = "Wind: " + response.data.list[0].wind.speed + 'm/s';
          this.overcast = response.data.list[0].weather[0].description;
          this.icon = "http://openweathermap.org/img/w/" + response.data.list[0].weather[0].icon + ".png";

          // AUJOURD'HUI + 1
          this.date1 = response.data.list[8].dt_txt;
          this.currentTemp1 = response.data.list[8].main.temp + "°";
          this.minTemp1 = response.data.list[8].main.temp_min + "°";
          this.maxTemp1 = response.data.list[8].main.temp_max + "°";
          this.icon1 = "http://openweathermap.org/img/w/" + response.data.list[8].weather[0].icon + ".png";

          // AUJOURD'HUI +2
          this.date2 = response.data.list[16].dt_txt;
          this.currentTemp2 = response.data.list[16].main.temp + "°";
          this.minTemp2 = response.data.list[16].main.temp_min + "°";
          this.maxTemp2 = response.data.list[16].main.temp_max + "°";
          this.icon2 = "http://openweathermap.org/img/w/" + response.data.list[16].weather[0].icon + ".png";

          // AUJOURD'HUI +3
          this.date3 = response.data.list[24].dt_txt;
          this.currentTemp3 = response.data.list[24].main.temp + "°";
          this.minTemp3 = response.data.list[24].main.temp_min + "°";
          this.maxTemp3 = response.data.list[24].main.temp_max + "°";
          this.icon3 = "http://openweathermap.org/img/w/" + response.data.list[24].weather[0].icon + ".png";

          // AUJOURD'HUI +4
          this.date4 = response.data.list[32].dt_txt;
          this.currentTemp4 = response.data.list[32].main.temp + "°";
          this.minTemp4 = response.data.list[32].main.temp_min + "°";
          this.maxTemp4 = response.data.list[32].main.temp_max + "°";
          this.icon4 = "http://openweathermap.org/img/w/" + response.data.list[32].weather[0].icon + ".png";

          TweenMax.fromTo('.dayDiv', 1, {y:300}, {y:0});

          TweenMax.fromTo('.extremiteL', 1, {x:-300}, {x:0});
          TweenMax.fromTo('.extremiteR', 1,{x:300},{x:0});

        })

    },
  },
  mounted() {

    TweenMax.from('#logo', 2, {y:-200})
    // TimelineLite.to(, 1, {x: 200,rotation: 90 })
  },
  props:{
      cityy : String,
      date :String,
      cityy : String,
      currentTemp :String,
      minTemp :String,
      maxTemp :String,
      pressure:String,
      humidity:String,
      wind :String,
      overcast:String,
      icon:String,

      date1 :String,
      currentTemp1 :String,
      minTemp1 :String,
      maxTemp1 :String,
      icon1:String,

      date2 :String,
      currentTemp2 :String,
      minTemp2 :String,
      maxTemp2 :String,
      icon2:String,

      date3 :String,
      currentTemp3 :String,
      minTemp3 :String,
      maxTemp3 :String,
      icon3:String,

      date4 :String,
      currentTemp4 :String,
      minTemp4 :String,
      maxTemp4 :String,
      icon4:String,
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.dayDiv {
  display: none;
}

.dayDiv1 {

}

.indi{
  margin-right: 2px;
  background-color:rgba(74, 89, 87, 0.20);

}
.secondaire{
  font-weight: bolder;
  color: #868686;
}

.extremiteDayMin{
  padding-top:15px;
}

.extremiteDayMax{

  padding-top:15px;
}


.grey {
  font-size: 25px;
  text-shadow: 2px 2px  black;
}


.box1 h1{
  color:#417505;
}

h1 {
  color: black;
}

.city1 {
  margin: 40px;
}

#logo {
  width: 200px;
  margin-top: 20px;
}

</style>
