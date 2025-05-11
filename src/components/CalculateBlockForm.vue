<template>
  <div
    class="bg-white rounded-xl p-6 w-[556px] 2xl:w-[858px]">
    <div
      class="mb-6">
      <div
        class="mb-3">
        <CalculateBlockFormInput
          v-model="name"
          name="name"
          label="ФИО"
          placeholder="Введите свои ФИО"/>
        <div
          v-if="nameError"
          class="mt-2">
          <CalculateBlockFormErrorMessage/>
        </div>
      </div>
      <div
        class="mb-3">
        <CalculateBlockFormInput
          v-model="email"
          name="email"
          label="Почта"
          placeholder="Введите почту"/>
        <div
          v-if="emailError"
          class="mt-2">
          <CalculateBlockFormErrorMessage/>
        </div>
      </div>
      <div
        class="mb-3">
        <CalculateBlockFormInput
          v-model="phone"
          name="phone"
          label="Телефон"
          placeholder="+7 (999) 999-99-99"/>
      </div>
      <div class="flex items-center gap-2">
          <input id="link-checkbox" type="checkbox" v-model="isChecked" class="w-12 h-12 text-[#46BFB3] bg-gray-100 accent-[#46BFB3] border-gray-300 rounded  focus:ring-[#46BFB3]">
          <label for="link-checkbox">Нажимая на чекбокс, Вы подтверждаете 
            <a href="/Согласие на обработку персональных данных.pdf" target="_blank" class="text-[#46BFB3]  hover:underline">согласие на обработку персональных данных</a> 
            и ознакомлены с <a href="/Политика конфиденциальности в отношении обработки персональных данных.pdf" target="_blank" class="text-[#46BFB3] hover:underline">политикой конфиденциальности</a>
          </label>
      </div>
    </div>
    <div
      :class="{
        ['rounded-[8px] h-[63px] flex justify-center items-center text-2xl']: true,
        ['cursor-pointer bg-[#46BFB3] text-white h-[63px] flex justify-center items-center text-2xl']: isChecked,
        ['cursor-not-allowed bg-[#c4c4c4] text-[#6a6a6a]']: !isChecked
      }"
      @click="onSendRequestClick">
      {{ sendButtonTitle }}
    </div>
  </div>
</template>

<script setup>
import CalculateBlockFormInput from './CalculateBlockFormInput.vue'
import CalculateBlockFormErrorMessage from './CalculateBlockFormErrorMessage.vue'

import { computed, ref } from 'vue' 

const emits = defineEmits('request:sended')

const name = ref('')
const nameError = ref(false)
const email = ref('')
const emailError = ref(false)
const phone = ref('')
const isChecked = ref(false)

const request = computed(() => {
  return {
    name: name.value,
    email: email.value,
    phone: phone.value
  }
})

function validateName() {
  if (!name.value) {
    nameError.value = true
  } else {
    nameError.value = false
  }
}

function validateEmail() {
  if (!email.value) {
    emailError.value = true
  } else {
    emailError.value = false
  }
}

const isFormValid = computed(() => !nameError.value && !emailError.value)
const isDisabled = ref(false)

const sendButtonTitle = computed(() => {
  if (isDisabled.value) {
    return 'Отправка данных...'
  } else {
    return 'Отправить запрос'
  }
})

function vaidateForm() {
  validateName()
  validateEmail()
}

function onSendRequestClick() {
  if (!isChecked.value) return;

  vaidateForm()
  if (isFormValid.value && !isDisabled.value) {
    try {
      isDisabled.value = true
      const requestOptions = {
        method: "GET",
        redirect: "follow",
      };
      fetch(`https://script.google.com/macros/s/AKfycbxhlQwX3O4wRhCwHfPJhLLCyNx2L2OJ6jaWxlnhGcbAXZtnbxn9B1xF-fi-p4EloGT4/exec?fio=${request.value.name}&email=${request.value.email}&phone=${request.value.phone}`, requestOptions).then(() => {
        emits('request:sended')
        isDisabled.value = false
      })
    } catch(e) {
      isDisabled.value = false
    }
  }
}
</script>

<style>

</style>