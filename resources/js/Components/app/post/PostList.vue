<script setup>
import PostItem from "@/Components/app/post/PostItem.vue"

const post1 = {
  user: {
    id: 1,
    avatar: "https://randomuser.me/api/portraits/men/17.jpg",
    name: "john smith",
  },
  group: null,
  body: `<p>Lorem ipsum xxx, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>`,
  created_at: "2023-11-12 15:13",
}
const post2 = {
  user: {
    id: 1,
    avatar: "https://randomuser.me/api/portraits/men/15.jpg",
    name: "michael angelo",
  },
  group: null,
  body: `<p>Lorem ipsum xxx, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  Lorem ipsum xxx, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>`,
  created_at: "2023-11-12 15:13",
}
</script>

<template>
  <div>
    <PostItem :item="post1" />
    <PostItem :item="post2" />
    <PostItem :item="post2" />
    <!-- <PostItem /> -->
  </div>
</template>

<style scoped></style>
