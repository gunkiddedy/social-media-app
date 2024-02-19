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
  description: {
    default:
      "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eius debitis sequi commodi, ipsa, quae animi obcaecati dignissimos dolor vel dolorem atque placeat quos rerum ab odit laudantium minus laborum reiciendis.",
    type: String,
  },
})
</script>

<template>
  <!-- group wraper -->
  <div class="group-item p-4 shadow-sm mb-3 bg-white">
    <img
      :src="image"
      :alt="title"
      class="w-20 h-20 rounded-full shadow-md border-2 border-gray-100"
    />
    <div class="group-info">
      <h3 class="text-xl font-bold capitalize">{{ title }}</h3>
      <p class="desc text-gray-500 text-sm">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<style scoped></style>
