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
      Отправить запрос
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
    name: name,
    email: email,
    phone: phone
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

function vaidateForm() {
  validateName()
  validateEmail()
}

function onSendRequestClick() {
  vaidateForm()
  if (isFormValid.value) {
    try {
      console.log(request.value)
      emits('request:sended')
    } catch(e) {

    }
  }
}
</script>