<script setup>
import Button from "../../generics/Button/Button.vue";
</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="hero__inner">
        <div class="hero__banner">
          <picture>
            <source media="(max-width: 600px)" srcset="@/assets/images/hero-banner-mobile.jpg">
            <img
              src="@/assets/images/hero-banner.jpg"
              alt="Домашняя кухня в центре города"
              loading="lazy"
              class="hero__banner-img"
            />
          </picture>
        </div>
        <div class="hero__content">
          <h2 class="hero__content-title">Домашняя кухня в центре города</h2>
          <p class="hero__content-description">
            Бронируйте стол онлайн — мы подготовим всё к вашему приходу.
          </p>
          <Button type="link" href="#form" color="accent"
            >Забронировать стол</Button
          >
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped src="./Hero.scss" />
