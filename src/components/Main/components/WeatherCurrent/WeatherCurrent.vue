<template>
  <div class="weather-card">
    <div class="time-now">
      Сейчас
    </div>
    <div class="card-info  flex-ai">
      <div class="weather-img">
        <img id="weather-img-card" src="" alt="weather img">
      </div>

      <div class="card-description">
        <div class="weather" id="weather-card"></div>
        <div class="degree"><span id="degree-card"></span>°C</div>
        <div class="card-line"></div>
        <div class="weather-stats flex-ai">
          <div class="weather-stat-left">
            <img src="./images/windy-stat.svg" alt="weather img">
            <span id="windy"></span>м/c
          </div>
          <div class="weather-stat-right">
            <img src="./images/humidity-stat.svg" alt="weather img">
            <span id="humidity"></span>см
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const link2 = 'http://api.weatherapi.com/v1/forecast.json?key=441bf2ddfa79478cbfc170201232704&q=Almaty&days=2&aqi=no&alerts=no';

async function fetchDataCurrent() {
  const result = await fetch(link2)
  const data = await result.json()

  document.querySelector('#degree-header').innerHTML = Math.round(data.current.temp_c);
  document.querySelector('#degree-card').innerHTML = Math.round(data.current.temp_c);
  document.querySelector('#windy').innerHTML = data.current.wind_mph;
  document.querySelector('#humidity').innerHTML = data.current.humidity;

  document.querySelector('#weather-card').innerHTML = data.current.condition.text;
  document.querySelector('#weather-img-card').src = data.current.condition.icon;
  document.querySelector('#weather-img-header').src = data.current.condition.icon;
}

fetchDataCurrent();
</script>

<style lang="scss">
@import './WeatherCurrent.scss';
</style>