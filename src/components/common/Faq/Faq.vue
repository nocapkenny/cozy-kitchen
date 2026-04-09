<script setup>
import Accordion from "../../generics/Accordion/Accordion.vue";

const faqElements = [
  {
    question: "Часы работы",
    answer: "Пн–Чт 10:00–22:00 · Пт–Сб 10:00–23:00 · Вс 11:00–21:00",
  },
  {
    question: "Как добраться",
    answer: "м. Тверская, 5 минут пешком. Вход со двора, домофон 42.",
  },
  {
    question: "Детям и особые пожелания",
    answer:
      "Детское меню и стульчики. Сообщите об аллергиях в форме бронирования.",
  },
];
</script>

<template>
  <section class="faq">
    <div class="container">
      <h2 class="faq__title">Частые вопросы</h2>
      <div class="faq__accordion">
        <Accordion :elements="faqElements" />
      </div>
    </div>
  </section>
</template>

<style scoped src="./Faq.scss" />
