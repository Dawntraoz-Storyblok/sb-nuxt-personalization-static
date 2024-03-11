<template>
  <div v-editable="blok">
    <NuxtLink
      :to="`/${blok.link.story.url}`"
      class="flex rounded-lg shadow-sm bg-white mt-10 p-[30px] w-2/5 container mx-auto"
    >
      <div class="flex-auto pr-50">
        <h2 class="text-3xl font-bold font-serif text-primary mb-4">
          {{ blok.headline }}
        </h2>
        <p class="text">{{ blok.text }}</p>
      </div>
      <div class="flex-none w-1/3 relative">
        <img
          :src="`${blok.image.filename}/m/500x300/smart/`"
          :alt="blok.image.alt"
          class="h-[200px] w-full object-cover"
        />
      </div>
    </NuxtLink>
  </div>
</template>

<script setup>
const props = defineProps({ blok: Object });
</script>
