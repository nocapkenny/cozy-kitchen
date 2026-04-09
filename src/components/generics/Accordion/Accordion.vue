<script setup>
import { onMounted, ref } from "vue";

const props = defineProps({
  elements: {
    type: Array,
    default: [],
  },
});

const itemsList = ref([]);

const openAccordion = (index) => {
    itemsList.value[index].isOpen = !itemsList.value[index].isOpen
};

onMounted(() => {
  itemsList.value = props.elements.map((element) => {
    return {
      question: element.question,
      answer: element.answer,
      isOpen: false,
    };
  });
});
</script>

<template>
  <div class="accordion">
    <div
      class="accordion__item"
      v-for="(element, index) in itemsList"
      :key="element.question"
      :class="itemsList[index].isOpen ? 'active' : ''"
    >
      <div class="accordion__item-question" @click="openAccordion(index)">
        {{ element.question }}
        <span>-</span>
      </div>
      <div class="accordion__item-answer">
        {{ element.answer }}
      </div>
    </div>
  </div>
</template>

<style scoped src="./Accordion.scss" />
