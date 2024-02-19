<script setup>
import PostItem from "@/Components/app/post/PostItem.vue"

const post1 = {
  user: {
    id: 1,
    avatar: "https://randomuser.me/api/portraits/men/17.jpg",
    name: "john smith",
  },
  group: null,
  attachments: [
    {
      id: 1,
      name: "test.png",
      url: "https://plus.unsplash.com/premium_photo-1678565869434-c81195861939?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      mime: "image/png",
    },
    {
      id: 2,
      name: "test2.png",
      url: "https://images.unsplash.com/photo-1605379399642-870262d3d051?q=80&w=1206&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      mime: "image/png",
    },
    {
      id: 3,
      name: "test2.png",
      url: "https://images.unsplash.com/photo-1605379399642-870262d3d051?q=80&w=1206&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      mime: "image/png",
    },
    {
      id: 4,
      name: "document-test.docx",
      url: "#",
      mime: "application/msword",
    },
  ],
  body: `<p>Lorem ipsum xxx, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  Lorem ipsum xxx, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>
  <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illum consequuntur nostrum harum commodi, fugiat recusandae iste tempora dicta eum in iure aliquam quae perferendis cum nisi. Minima, omnis voluptas!</p>`,
  created_at: "2023-11-12 15:13",
}
const post2 = {
  user: {
    id: 1,
    avatar: "https://randomuser.me/api/portraits/men/15.jpg",
    name: "michael angelo",
  },
  group: {
    id: 1,
    name: "Laravel",
  },
  attachments: [
    {
      id: 1,
      name: "test.png",
      url: "https://plus.unsplash.com/premium_photo-1678565869434-c81195861939?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      mime: "image/png",
    },
  ],
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
