<script setup>
import IInput from '@/components/IInput/IInput.vue'
import FormContainer from '../FormContainer.vue'
import { reactive, toRaw, watch } from 'vue'
import IButton from '@/components/IButton/IButton.vue'

const emit = defineEmits(['submit'])
const userData = reactive({
  email: '',
  password: ''
})

watch(userData, () => {
  console.log('user data input')
})
</script>

<template>
  <FormContainer @submit.prevent="emit('submit', toRaw(userData))">
    <IInput class="mb-4" placeholder="email@email.com" v-model="userData.email" />
    <IInput type="password" placeholder="Пароль" v-model="userData.password" />
    <IButton class="mt-10 w-full" variant="gradient" type="submit">Увійти</IButton>
  </FormContainer>
</template>
