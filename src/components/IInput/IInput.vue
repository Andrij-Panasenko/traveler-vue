<script setup>
import { ref } from 'vue'

const props = defineProps({
  label: String
})

const inputValue = ref('')

const changeValue = (evt) => {
  inputValue.value = evt.target.value
}
</script>

<template>
  <div class="w-full text-[#2C2C2C]">
    <label class="block">
      <span class="block text-xs px-3 mb-2">{{ props.label }}: {{ inputValue }}</span>
      <input
        @input="changeValue"
        class="w-full text-sm rounded-[4px] border-[#eaeaea] border-[1px] py-2 px-3 focus:outline-primary"
        type="text"
      />
    </label>
  </div>
</template>
