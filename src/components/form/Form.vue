<script lang="ts" setup>

import {string} from 'yup'

import Field from './Field.vue'
import Button from './Button.vue'

</script>

<template>
  <form class="form">
    <Field
      name="full-name"
      type="text"
      label="ФИО"
      placeholder="Введите ваше ФИО"
    />
    <Field
      name="date"
      type="number"
      label="Дата рождения"
      placeholder="Укажите дату рождения"
      :validator="string().required('Пожалуйста, заполните поле').email('Неверный формат даты')"
    />
    <Field
      name="telephone"
      type="tel"
      label="Номер телефона"
      placeholder="Введите номер телефона"
      :validator="string().required('Пожалуйста, заполните поле').email('Телефон не корректный')"
    />
    <Field
      name="email"
      type="email"
      label="Электронная почта"
      placeholder="Укажите электронную почту"
      :validator="string().required('Пожалуйста, заполните поле').email('E-mail не корректный')"
    />
    <Button
      label="Далее"
      type="submit"
    />
  </form>
  
</template>

<style scoped>

.form {
  max-width: 800px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 15px;
}

</style>
