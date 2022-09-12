<script lang="ts" setup>
defineProps<{ image: string; name: string; link: string }>();
</script>

<template>
  <div class="p-4 w-4/12">
    <div
      class="rounded-xl bg-white shadow-md duration-200 hover:scale-105 hover:shadow-xl"
    >
      <div
        class="bg-cover bg-center bg-no-repeat h-96"
        :style="{ backgroundImage: `url(${image})` }"
      />

      <div class="p-5">
        <p class="text-medium mb-5 text-gray-700">{{ name }}</p>
        <a
          :href="link"
          class="block no-underline cursor-pointer text-center w-full rounded-md bg-indigo-600 py-2 text-indigo-100 hover:bg-indigo-500 hover:shadow-md duration-75"
          >See More</a
        >
      </div>
    </div>
  </div>
</template>
