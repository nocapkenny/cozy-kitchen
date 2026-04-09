<script setup>
import Button from '../../generics/Button/Button.vue';

const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false,
    }
})

const emits = defineEmits(['close-modal'])

</script>

<template>
  <div v-if="props.isOpen" class="modal" :class="props.isOpen ? 'open' : ''">
    <div class="modal-overlay" @click="emits('close-modal')"></div>
    <div class="modal-content">
      <div class="modal-content__inner">
        <p class="modal-content__title">Заявка отправлена</p>
        <p class="modal-content__description">
          Спасибо! Мы свяжемся с Вами в ближайшее время для подтверждения брони.
        </p>
        <Button type="button" color="grey" @click="emits('close-modal')">Закрыть</Button>
      </div>
    </div>
  </div>
</template>

<style src="./Success.scss" />
