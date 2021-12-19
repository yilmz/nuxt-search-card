<template>
  <div class="p-10">
    <div
      class="
        max-w-sm
        rounded
        overflow-hidden
        shadow-lg
        h-60
        max-h-full
        md:max-h-screen
        hover:h-full
        bg-white
      "
    >
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2 text-gray-700">{{ post.title }}</div>
        <p class="text-gray-700 text-base">
          {{ post.body }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
    },
  },
};
</script>

<style>
</style>