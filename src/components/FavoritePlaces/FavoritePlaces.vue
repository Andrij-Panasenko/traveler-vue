<script setup>
import FavoritePlace from '../FavoritePlace/FavoritePlace.vue'
import IButton from '../IButton/IButton.vue'
import { ref } from 'vue'
import IInput from '../IInput/IInput.vue'

const buttonVariant = ref('gradient')

const changeBtnVariant = () => {
  buttonVariant.value = buttonVariant.value === 'gradient' ? 'outlined' : 'gradient'
}
</script>

<template>
  <div class="px-6">
    <div class="text-gray mb-4">Додані маркери: {{ buttonVariant }}</div>
    <div class="py-5">
      <IInput label="Some label" />
    </div>
    <FavoritePlace v-for="n in 4" :key="n" />
    <IButton class="w-full mt-10" :variant="buttonVariant" @click="changeBtnVariant"
      >Додати маркер</IButton
    >
  </div>
</template>
