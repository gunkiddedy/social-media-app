<script setup>
import { onMounted } from "vue"
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue"

const props = defineProps({
  item: Object,
})

const isImage = (attachment) => {
  const mime = attachment.mime.split("/")
  return mime[0].toLowerCase() === "image"
}

onMounted(() => {
  console.log("item", props.item)
})
</script>

<template>
  <div class="post-item px-8 py-4 shadow-sm mb-3 bg-white">
    <!-- header -->
    <div class="flex items-center space-x-2">
      <img
        class="rounded-full w-11 h-11 hover:ring-2 transition-all hover:ring-gray-300 hover:scale-110"
        :src="item.user.avatar"
        :alt="item.user.name"
      />
      <div>
        <div class="flex items-center space-x-2">
          <a href="">
            <h4
              class="text-gray-400 font-semibold capitalize leading-none hover:underline"
            >
              {{ item.user.name }}
            </h4>
          </a>
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

    <!-- descriptions -->
    <Disclosure v-slot="{ open }">
      <div
        v-if="!open"
        class="body text-base text-gray-500 font-medium leading-snug"
        v-html="item.body.substring(0, 300) + '...'"
      />

      <DisclosurePanel class="">
        <div
          class="body text-base text-gray-500 font-medium leading-snug"
          v-html="item.body"
        />
      </DisclosurePanel>

      <div v-if="item.body.length > 300" class="flex justify-end">
        <DisclosureButton class="mb-2">
          <span class="text-indigo-500 text-sm hover:underline">
            {{ open ? "read less" : "read more" }}
          </span>
        </DisclosureButton>
      </div>
    </Disclosure>

    <!-- attachments -->
    <div class="attachments-container grid grid-cols-2">
      <div
        class="attachments"
        v-for="attachment in item.attachments"
        :key="attachment.id"
      >
        <div
          v-if="isImage(attachment)"
          class="img w-[335px] h-[225px] bg-rose-300"
        >
          <img
            class="img-attachment object-cover w-full h-full"
            :src="attachment.url"
            alt=""
          />
        </div>
        <div
          v-else
          class="document bg-gray-100 text-base text-gray-400 w-full h-full flex flex-col items-center justify-center"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-10 h-10"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M19.5 14.25v-2.625a3.375 3.375 0 0 0-3.375-3.375h-1.5A1.125 1.125 0 0 1 13.5 7.125v-1.5a3.375 3.375 0 0 0-3.375-3.375H8.25m0 12.75h7.5m-7.5 3H12M10.5 2.25H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 0 0-9-9Z"
            />
          </svg>

          <a href="" class="hover:underline">
            {{ attachment.name }}
          </a>
        </div>
      </div>
    </div>

    <!-- comments & like -->
    <div class="like-comments flex justify-between items-center mt-3">
      <button
        type="button"
        class="border border-gray-500 rounded px-3 py-0.5 text-gray-500 like"
      >
        like
      </button>
      <button
        type="button"
        class="border border-gray-500 rounded px-3 py-0.5 text-gray-500 comment"
      >
        comment
      </button>
    </div>
  </div>
</template>

<style scoped></style>
