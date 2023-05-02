<template>
  <header>
    <div class="container">
      <div class="header-wrapper flex-ai">

        <div class="header-left-side flex-ai">
          <div class="header-logo left-logo">
            <a href="/">
              <img src="./images/logo.svg" alt="logo" class="logo-img">
            </a>
          </div>
          <div class="burger-menu" id="burger-menu" v-on:click="showMenu()">
            <img src="./images/menu-burger.svg" alt="menu" class="img-menu">
          </div>
          <button class="burger-btn-header-close" id="burger-menu-close" v-on:click="closeMenu()">
            <img src="./images/menu-burger-close.svg" alt="menu">
          </button>
          <div class="header-live flex-ai element-props">
            <img src="./images/icon-live-red.svg" alt="live" class="live-img mr">
            LIVE
          </div>
          <div class="header-weather flex-ai element-props">
            <img src="" alt="weather" class="weather-img mr" id="weather-img-header">
            <span id="degree-header"></span>C°
          </div>
          <div class="header-season flex-ai element-props">
            <span class="active-weather mr">Лето</span>
            <span class="off-weather">Зима</span>
          </div>
          <div class="header-search flex-ai element-props">
            <img src="./images/icon-loupe.svg" alt="search" class="img-search">
          </div>
        </div>

        <div class="center-logo">
          <a href="/">
            <img src="./images/logo.svg" alt="logo" class="logo-img">
          </a>
        </div>

        <div class="header-right-side flex-ai">
          <div class="header-lang flex-ai element-props">
            RU
          </div>
          <div class="header-user flex-ai element-props">
            <img src="./images/icon-user.svg" alt="search" class="img-user">
          </div>
          <div class="header-favorite flex-ai element-props">
            <img src="./images/icon-favorites.svg" alt="search" class="img-favorite">
          </div>
          <div class="header-cart flex-ai element-props">
            <img src="./images/icon-cart.svg" alt="search" class="img-cart">
          </div>
        </div>
        
      </div>
    </div>
  </header>
</template>

<script setup>
function showMenu() {
  document.querySelector('#aside').classList.toggle('show');
  document.querySelector('#burger-menu').style.display = 'none';
  document.querySelector('#burger-menu-close').style.display = 'block';
  document.querySelector('#aside-wrapper').classList.toggle('aside-wrapper');
  document.body.style.overflowY = 'hidden';
  document.body.height = '100vh';
}
function closeMenu() {
  document.querySelector('#aside').classList.toggle('show');
  document.querySelector('#burger-menu').style.display = 'block';
  document.querySelector('#burger-menu-close').style.display = 'none';
  document.querySelector('#aside-wrapper').classList.toggle('aside-wrapper');
  document.body.style.overflowY = 'auto';
  document.body.height = '100%';
}
</script>

<style lang="scss">
@import 'Header.scss';
</style>