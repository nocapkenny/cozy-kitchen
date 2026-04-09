<script setup>
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { Navigation, Pagination } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";

const props = defineProps({
  slidesPerView: {
    type: Number,
    default: 1,
  },
  spaceBetween: {
    type: Number,
    default: 0,
  },
  slides: {
    type: Array,
    default: [],
  },
});
</script>

<template>
  <div class="slider">
    <Swiper
      :modules="[Navigation, Pagination]"
      :slides-per-view="props.slidesPerView"
      :slides-per-group="1"
      :space-between="props.spaceBetween"
      :navigation="{
        nextEl: '.slider__next',
        prevEl: '.slider__prev',
      }"
      :breakpoints="{
        320: { slidesPerView: 1 },
        768: { slidesPerView: 2 },
        1200: { slidesPerView: 3 },
      }"
      :pagination="{
        el: '.slider__pagination',
        clickable: true,
        renderBullet: (index, className) => {
          return `<span class='${className}'></span>`;
        },
      }"
    >
      <SwiperSlide v-for="(slide, index) in props.slides" :key="slide">
        <img class="slider__img" :src="slide" :alt="'Картинка' + (index + 1)" />
      </SwiperSlide>
    </Swiper>
    <div class="slider__pagination"></div>
    <div class="slider__prev">
      <button class="slider__prev-btn">
        <svg
          width="40"
          height="40"
          viewBox="0 0 40 40"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect x="0.5" y="0.5" width="39" height="39" rx="19.5" fill="white" />
          <rect
            x="0.5"
            y="0.5"
            width="39"
            height="39"
            rx="19.5"
            stroke="#E0D8CE"
          />
          <path
            d="M22.3182 26.625H20.5455L17.1023 21.5114V21.3409H19.0455L22.3182 26.625ZM22.3182 16.1591L19.0455 21.4432H17.1023V21.2727L20.5455 16.1591H22.3182Z"
            fill="#2C2416"
          />
        </svg>
      </button>
    </div>
    <div class="slider__next">
      <button class="slider__next-btn">
        <svg
          width="40"
          height="40"
          viewBox="0 0 40 40"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect x="0.5" y="0.5" width="39" height="39" rx="19.5" fill="white" />
          <rect
            x="0.5"
            y="0.5"
            width="39"
            height="39"
            rx="19.5"
            stroke="#E0D8CE"
          />
          <path
            d="M17.1023 26.625L20.375 21.3409H22.3182V21.5114L18.875 26.625H17.1023ZM17.1023 16.1591H18.875L22.3182 21.2727V21.4432H20.375L17.1023 16.1591Z"
            fill="#2C2416"
          />
        </svg>
      </button>
    </div>
  </div>
</template>

<style src="./Slider.scss" />
