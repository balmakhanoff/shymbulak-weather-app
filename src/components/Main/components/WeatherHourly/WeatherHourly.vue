<template>
  <div class="weather-hourly">
    <div class="time-hourly">
      Погода в течении дня
    </div>
    <div class="card-line"></div>
    <div class="hours-content-flex flex-ai">
      <button>&lt;</button>
      <div class="hours-content">

        <div class="hour-card-wrapper flex-ai">
        </div>

      </div>
      <button>&gt;</button>
    </div>

  </div>
</template>

<script>
const link1 = 'http://api.weatherapi.com/v1/forecast.json?key=441bf2ddfa79478cbfc170201232704&q=Almaty&days=2&aqi=no&alerts=no';
let date = new Date();
let hours = date.getHours();

async function getFetchHourly() {
  const result = await fetch(link1);
  const data = await result.json();

  for (let i = 0; i < 10; i++) {
    let num = 0;
    if (hours > 23) {
      hours = 0;
      num + 1;
    }

    document.querySelector('.hour-card-wrapper').innerHTML += `
        <div class="hour-card">
          <p class="hour-time" id="hour-time">
            ${data.forecast.forecastday[num].hour[hours].time.slice(11, -3)}
          </p>
          <div class="hour-img">
            <img id="hour-img" src=${data.forecast.forecastday[num].hour[hours].condition.icon} alt="weather">
          </div>          
          <p class="hour-degree" id="hour-degree">
            ${Math.round(data.forecast.forecastday[num].hour[hours].temp_c)}
          </p>
        </div>
    `
    hours++
  }
}

getFetchHourly();
</script>

<style lang="scss">
@import './WeatherHourly.scss';

marquee {
  display: block;
}
</style>