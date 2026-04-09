<script setup>
import Slider from "../../generics/Slider/Slider.vue";

const pictures = [
  "/src/assets/images/slide1.png",
  "/src/assets/images/slide2.png",
  "/src/assets/images/slide3.png",
  "/src/assets/images/slide4.png",
  "/src/assets/images/slide5.png",
  "/src/assets/images/slide6.png",
  "/src/assets/images/slide7.png",
  "/src/assets/images/slide8.png",
  "/src/assets/images/slide9.png",
];
</script>

<template>
  <section class="gallery">
    <div class="container">
      <div class="gallery__inner">
        <p class="gallery__ask">
          <span class="gallery__ask--text">Нравится атмосфера?</span>
          <a class="gallery__ask--link" href="#form"
            >перейти к форме бронирования</a
          >
        </p>
        <Slider :spaceBetween="16" :slidesPerView="3" :slides="pictures" />
      </div>
    </div>
  </section>
</template>

<style src="./Gallery.scss" scoped />
