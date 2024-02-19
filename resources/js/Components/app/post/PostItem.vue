<script setup>
import { onMounted } from "vue"
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue"

const props = defineProps({
  item: Object,
})

const isImage = (file) => {
  const mime = file.mime.split("/")
  return mime[0].toLowerCase() === "image"
}

onMounted(() => {
  console.log("item", props.item)
})
</script>

<template>
  <div class="post-item p-8 shadow-sm mb-3 bg-white">
    <!-- header -->
    <a href="">
      <div class="flex items-center space-x-2">
        <img
          class="rounded-full w-11 h-11 hover:ring-2 transition-all hover:ring-gray-300 hover:scale-110"
          :src="item.user.avatar"
          :alt="item.user.name"
        />
        <div>
          <div class="flex items-center space-x-2">
            <h4
              class="text-gray-400 font-semibold capitalize leading-none hover:underline"
            >
              {{ item.user.name }}
            </h4>
            <div
              v-if="item.group"
              class="group-name text-gray-400 font-semibold capitalize"
            >
              >
              <a class="hover:underline" href="#">
                {{ item.group.name }}
              </a>
            </div>
          </div>
          <small class="text-gray-400 text-xs">{{ item.created_at }}</small>
        </div>
      </div>
    </a>

    <!-- body -->
    <Disclosure v-slot="{ open }">
      <div
        v-if="!open"
        class="body text-base text-gray-500 font-medium leading-snug"
        v-html="item.body.substring(0, 300)"
      />

      <DisclosurePanel class="">
        <div
          class="body text-base text-gray-500 font-medium leading-snug"
          v-html="item.body"
        />
      </DisclosurePanel>

      <div v-if="item.body.length > 300" class="flex justify-end">
        <DisclosureButton class="mb-2">
          <span class="text-gray-400 text-sm hover:underline">
            {{ open ? "read less" : "read more" }}
          </span>
        </DisclosureButton>
      </div>
    </Disclosure>

    <!-- attachments -->
    <div class="attachments grid grid-cols-2 gap-2">
      <div
        class="attachment"
        v-for="attachment in item.attachments"
        :key="attachment.id"
      >
        <img v-if="isImage" class="shadow-sm" :src="attachment.url" alt="" />
      </div>
    </div>

    <!-- comments & like -->
    <div class="like-comments flex justify-between items-center mt-3">
      <button
        type="button"
        class="bg-rose-500 rounded px-3 py-0.5 text-white like"
      >
        like
      </button>
      <button
        type="button"
        class="bg-rose-500 rounded px-3 py-0.5 text-white comment"
      >
        comment
      </button>
    </div>
  </div>
</template>

<style scoped></style>
