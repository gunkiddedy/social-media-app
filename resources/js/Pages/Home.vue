<script setup>
import { Head, Link } from "@inertiajs/vue3"
import GroupList from "@/Components/app/groups/GroupList.vue"
import FollowingList from "@/Components/app/friends/FollowingList.vue"
import CreatePost from "@/Components/app/post/CreatePost.vue"
import PostList from "@/Components/app/post/PostList.vue"

defineProps({})
</script>

<template>
  <Head title="Home" />
  <div class="grid grid-cols-12 gap-1">
    <div class="col-span-3 p-4 relative">
      <GroupList class="fixed max-w-[350px]" />
    </div>

    <div class="col-span-6 p-4">
      <CreatePost />
      <PostList />
    </div>

    <div class="col-span-3 p-4 relative">
      <FollowingList class="fixed w-full max-w-[350px]" />
    </div>
  </div>
</template>

<style></style>
