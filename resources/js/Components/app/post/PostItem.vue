<script setup>
import { onMounted } from "vue"
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue"

const props = defineProps({
  item: Object,
})

onMounted(() => {
  console.log(item)
})
</script>

<template>
  <div class="post-item p-4 shadow-sm mb-3 bg-white">
    <a href="">
      <div class="flex items-center space-x-2">
        <img
          class="rounded-full w-11 h-11"
          :src="item.user.avatar"
          :alt="item.user.name"
        />
        <div>
          <h4 class="text-gray-600 font-semibold capitalize">
            {{ item.user.name }}
          </h4>
          <small class="text-gray-400">{{ item.created_at }}</small>
        </div>
      </div>
    </a>
    <Disclosure v-slot="{ open }">
      <div v-if="!open" class="body" v-html="item.body.substring(0, 300)" />

      <DisclosurePanel class="">
        <div v-html="item.body" />
      </DisclosurePanel>

      <div class="flex justify-end">
        <DisclosureButton class="">
          <span class="text-gray-400 text-sm">
            {{ open ? "read less" : "read more" }}
          </span>
        </DisclosureButton>
      </div>
    </Disclosure>
  </div>
</template>

<style scoped></style>
