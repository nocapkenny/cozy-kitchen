<script setup>
import Slider from "../../generics/Slider/Slider.vue";

import slide1 from '@/assets/images/slide1.png'
import slide2 from '@/assets/images/slide2.png'
import slide3 from '@/assets/images/slide3.png'
import slide4 from '@/assets/images/slide4.png'
import slide5 from '@/assets/images/slide5.png'
import slide6 from '@/assets/images/slide6.png'
import slide7 from '@/assets/images/slide7.png'
import slide8 from '@/assets/images/slide8.png'
import slide9 from '@/assets/images/slide9.png'

const pictures = [
  slide1,
  slide2,
  slide3,
  slide4,
  slide5,
  slide6,
  slide7,
  slide8,
  slide9,
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
