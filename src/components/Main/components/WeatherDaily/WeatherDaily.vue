<template>
  <section class="weather-daily">
    <div class="time-daily">
      Прогноз на 10 дней
    </div>
    <div class="daily-line"></div>
    <div class="daily-content-holder">
      <div class="daily-card-wrapper flex-ai">
      </div>
    </div>
  </section>
</template>

<script>
const link3 = 'http://api.weatherapi.com/v1/forecast.json?key=441bf2ddfa79478cbfc170201232704&q=Almaty&days=10&aqi=yes&alerts=no';
const months = ['январь', 'февраль', 'март', 'апрель', 'май', 'июнь', 'июль', 'августа', 'сентябрь', 'октябрь', 'ноябрь', 'декабрь'];
const days = ['ВС', 'ПН', 'ВТ', 'СР', 'ЧТ', 'ПТ', 'СБ'];
const date = new Date();
let dayString = date.getDay();

async function getFetchDaily() {
  const result = await fetch(link3);
  const data = await result.json();

  for (let i = 0; i < 10; i++) {
    const day = data.forecast.forecastday[i].date.slice(-2).replace(/^0+/, '');
    const month = data.forecast.forecastday[i].date.slice(5, 7);
    if (dayString > 6) {
      dayString = 0;
    }
    document.querySelector('.daily-card-wrapper').innerHTML += `
      <div class="daily-card">
        <div class="day">${days[dayString]} </div>
        <div class="day-date">
          ${day} ${months[month.replace(/^0+/, '') - 1]}  
        </div>
        <img src=${data.forecast.forecastday[i].day.condition.icon} alt="weather">
        <div class="min-weather">         
          мин. <span>${Math.round(data.forecast.forecastday[i].day.mintemp_c)}</span>°       
        </div>
        <div class="max-weather">
          макс. <span>${Math.round(data.forecast.forecastday[i].day.maxtemp_c)}
        </span>
        </div>
      </div>
    `
    dayString++;
  }

  document.querySelector('.day').innerHTML = 'Сегодня';

}

getFetchDaily();
</script>

<style lang="scss">
@import './WeatherDaily.scss';
</style>