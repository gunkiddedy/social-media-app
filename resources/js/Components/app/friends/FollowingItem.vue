<script setup>
defineProps({
  image: {
    default:
      "https://plus.unsplash.com/premium_photo-1678565869434-c81195861939?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    type: String,
  },
  title: {
    default: "laravel developers",
    type: String,
  },
})
</script>

<template>
  <!-- group wraper -->
  <div class="friend-item p-4 shadow-sm mb-3 bg-white">
    <img
      :src="image"
      :alt="title"
      class="w-20 h-20 rounded-full shadow-md border-2 border-gray-100"
    />
    <div class="group-info">
      <h3 class="text-xl font-bold capitalize">{{ title }}</h3>
    </div>
  </div>
</template>

<style scoped></style>
