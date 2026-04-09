<script setup>
import Button from "../../generics/Button/Button.vue";
import { onMounted, ref } from "vue";
import IMask from "imask";
import JustValidate from "just-validate";
import Sucess from "../../modals/Sucess/Sucess.vue";

const phoneInput = ref(null);
const formValues = ref({
  name: "",
  surname: "",
  email: "",
  phone: "",
});
const isModalOpen = ref(false)

const closeModal = () => {
  isModalOpen.value = false
}

onMounted(() => {
  IMask(phoneInput.value, {
    mask: "+{7} (000) 000-00-00",
  });

  const validate = new JustValidate("#form");

  validate
    .addField("#name", [
      {
        rule: "required",
        errorMessage: "Введите имя",
      },
    ])
    .addField("#surname", [
      {
        rule: "required",
        errorMessage: "Введите фамилию",
      },
    ])
    .addField("#phone", [
      {
        rule: "required",
        errorMessage: "Введите телефон",
      },
    ])
    .addField("#email", [
      {
        rule: "required",
        errorMessage: "Введите email",
      },
      {
        rule: "email",
        errorMessage: "Введите корректный email",
      },
    ]);

  validate.onSuccess(() => {
    formValues.value.phone = phoneInput.value.value
    console.log(formValues.value);
    isModalOpen.value = true
  });
});
</script>

<template>
  <section class="form-section" id="form">
    <div class="container">
      <div class="form-section__inner">
        <h3 class="form-section__title">Бронирование стола</h3>
        <p class="form-section__description">
          Заполните поля — перезвоним для подтверждения.
        </p>
        <form class="form-section__form">
          <div class="form-section__form-group">
            <label class="form-section__group-label" for="name">Имя</label>
            <input
              class="form-section__group-input"
              type="text"
              id="name"
              v-model="formValues.name"
            />
          </div>
          <div class="form-section__form-group">
            <label class="form-section__group-label" for="surname"
              >Фамилия</label
            >
            <input
              class="form-section__group-input"
              type="text"
              id="surname"
              v-model="formValues.surname"
            />
          </div>
          <div class="form-section__form-group">
            <label class="form-section__group-label" for="email">Email</label>
            <input
              class="form-section__group-input"
              type="text"
              id="email"
              v-model="formValues.email"
            />
          </div>
          <div class="form-section__form-group">
            <label class="form-section__group-label" for="phone">Телефон</label>
            <input
              class="form-section__group-input"
              type="text"
              id="phone"
              ref="phoneInput"
              v-model="formValues.phone"
            />
          </div>
          <Button color="green" button-type="submit" type="button" size="large"
            >Отправить</Button
          >
        </form>
      </div>
    </div>
  </section>
  <Sucess :isOpen="isModalOpen" @close-modal="closeModal"/>
</template>

<style src="./Form.scss" />
