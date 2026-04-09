<template>
  <header class="header">
    <div class="container">
      <div class="header__inner">
        <div class="header__logo">
          <div class="header__logo-box">
            <img
              class="header__logo-icon"
              src="../../../assets/icons/logo.svg"
              alt="logo"
            />
          </div>
          <h1 class="header__logo-text">
            Уютная <span class="header__logo-text--span">кухня</span>
          </h1>
        </div>
        <nav class="header__nav">
          <ul class="header__nav-list">
            <li class="header__list-item">
              <a href="#" class="header__item-link">Меню</a>
            </li>
            <li class="header__list-item">
              <a href="#form" class="header__item-link header__item-link--colored"
                >К бронированию</a
              >
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped src="./Header.scss" />
