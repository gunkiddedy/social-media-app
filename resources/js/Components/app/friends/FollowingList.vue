<script setup>
import { ref } from "vue"

import FollowingItem from "@/Components/app/friends/FollowingItem.vue"
import TextInput from "@/Components/TextInput.vue"

const searchKeyword = ref("")
</script>

<template>
  <div class="mygroups">
    <div class="section-title mb-3">
      <h2 class="text-2xl font-bold capitalize text-center">My groups</h2>
    </div>

    <div class="search mb-3">
      <TextInput
        v-model="searchKeyword"
        placeholder="search your friends"
        class="w-full"
      />
    </div>

    <div v-if="false" class="you-are-not text-gray-500 text-sm">
      you're not join to any groups
    </div>

    <div v-else class="my-groups">
      <FollowingItem title="go developers" />
      <FollowingItem title="vue developers" />
      <FollowingItem
        title="laravel developers"
        description="Lorem, ipsum dolor sit amet consectetur adipisicing elit."
        image="https://plus.unsplash.com/premium_photo-1678565869434-c81195861939?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
      />
    </div>
  </div>
</template>

<style scoped></style>
