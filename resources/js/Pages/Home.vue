<script setup>
import { Head, Link } from "@inertiajs/vue3"
import GroupList from "@/Components/app/groups/GroupList.vue"
import FollowingList from "@/Components/app/friends/FollowingList.vue"

defineProps({})
</script>

<template>
  <Head title="Home" />
  <div class="grid grid-cols-3 gap-x-1">
    <div class="p-4">
      <GroupList />
    </div>

    <div class="p-4">
      <div class="section-title mb-4 border-b border-gray-400 py-4">
        <h2 class="text-2xl font-bold capitalize text-center">My groups</h2>
      </div>

      <div v-if="false" class="you-are-not text-gray-500 text-sm">
        you're not join to any groups
      </div>

      <div v-else class="my-groups"></div>
    </div>

    <div class="p-4">
      <FollowingList />
    </div>
  </div>
</template>

<style></style>
