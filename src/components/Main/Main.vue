<template>
  <div class="container main-container">
    <AsideMenu />
    <main class="weather-wrapper">
      <h1>Погода</h1>
      <div class="weather-upper-side flex-ai">
        <WeatherCurrent />
        <WeatherHourly />
      </div>
      <div class="weather-bottom-side">
        <WeatherDaily />
      </div>
    </main>
  </div>
</template>
  
<script>
import AsideMenu from './components/AsideMenu/AsideMenu.vue';
import WeatherCurrent from './components/WeatherCurrent/WeatherCurrent.vue';
import WeatherHourly from './components/WeatherHourly/WeatherHourly.vue';
import WeatherDaily from './components/WeatherDaily/WeatherDaily.vue';

export default {
  name: 'Main',
  components: {
    AsideMenu, WeatherCurrent, WeatherHourly, WeatherDaily
  }
}

</script>

<style lang="scss">
@import '../../assets/styles/main.scss';

.main-container {
  display: flex;
  position: relative;

  .weather-wrapper {
    @include adaptive-value('padding-top', 24, 5, 1);
    @include adaptive-value('padding-left', 50, 5, 1);
    @include adaptive-value('padding-right', 50, 5, 1);
    @include adaptive-value('padding-bottom', 96, 24, 1);
    width: 100%;
    
    box-sizing:content-box;
  }

  h1 {
    @include adaptiv-font(40, 20);
    font-weight: 600;
    line-height: 48px;
    color: $COLOR_BLACK;
  }

  .weather-upper-side {
    @include adaptive-value('padding-top', 78, 35, 1);
    @include adaptive-value('padding-bottom', 48, 10, 1);
    column-gap: 24px;
    @include adaptive-value('height', 230, 190, 1);
    justify-content: space-between;
  }

  .weather-bottom-side {
    width: 100%;
  }
}

@media screen and (max-width: 767px) {

  .weather-upper-side {
    padding: 0 20px;
    flex-direction: column;
    row-gap: 32px;
    margin-bottom: 250px;
  }

}
</style>