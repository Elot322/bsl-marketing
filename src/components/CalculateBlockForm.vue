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
    </div>
    <div
      class="cursor-pointer rounded-[8px] bg-[#46BFB3] text-white h-[63px] flex justify-center items-center text-2xl"
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