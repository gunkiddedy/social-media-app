<script setup>
import { onMounted, ref } from "vue"

const model = defineModel({
  type: String,
  required: true,
})

defineProps({
  placeholder: {
    type: String,
    default: "Search groups",
  },
})

const input = ref(null)

onMounted(() => {
  if (input.value.hasAttribute("autofocus")) {
    input.value.focus()
  }
})

defineExpose({ focus: () => input.value.focus() })
</script>

<template>
  <input
    v-model="model"
    :placeholder="placeholder"
    class="border-gray-300 focus:border-indigo-500 focus:ring-indigo-500 rounded-md shadow-sm"
    ref="input"
  />
</template>
