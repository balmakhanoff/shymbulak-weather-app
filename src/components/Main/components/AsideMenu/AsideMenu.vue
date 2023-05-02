<template>
  <div id="aside-wrapper" v-on:click="asideBg()">
    <aside class="aside" id="aside">
      <nav>
        <ul class="nav-menu">

          <li class="menu-item ">
            <a href="/" class="menu-link ">
              <img src="./images/icon-main.svg" alt="main" class="menu-img mr">
              Главная
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-tickets.svg" alt="tickets" class="menu-img mr">
              Билеты
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-rent.svg" alt="rent" class="menu-img mr">
              Прокат
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-school.svg" alt="school" class="menu-img mr">
              Школа
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-entertainment.svg" alt="entertainment" class="menu-img mr">
              Развлечения
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-hotels.svg" alt="hotels" class="menu-img mr">
              Отели
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-restoraunt.svg" alt="restaurants" class="menu-img mr">
              Рестораны
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-shops.svg" alt="shops" class="menu-img mr">
              Магазин
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-kids.svg" alt="kids" class="menu-img mr">
              Детям
            </a>
          </li>
          <li class="menu-item">
            <a href="#" class="menu-link">
              <img src="./images/icon-parking.svg" alt="parking" class="menu-img mr">
              Паркинг
            </a>
          </li>

        </ul>
      </nav>

      <button class="btn-info">
        <img src="./images/btn-info.svg" alt="info" class="info-img mr">
        Инфо
      </button>
    </aside>
  </div>
</template>

<script setup>
function asideBg() {
  document.querySelector('#aside').classList.remove('show');
  document.querySelector('#aside-wrapper').classList.remove('aside-wrapper');
  document.querySelector('#burger-menu').style.display = 'block';
  document.querySelector('#burger-menu-close').style.display = 'none';
  document.body.style.overflowY = 'auto';
  document.body.height = '100%';
}
</script>

<style lang="scss">
@import 'AsideMenu.scss';
</style>