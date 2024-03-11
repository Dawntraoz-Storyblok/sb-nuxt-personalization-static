<script setup>
const { slug } = useRoute().params;
const url = slug && slug.length > 0 ? slug.join("/") : "home";

const story = await useAsyncStoryblok(url.replace(/\/$/, ""), {
  version: "draft",
  resolve_links: "story",
});
</script>

<template>
  <main v-if="story" class="bg-teal-100 flex-auto">
    <h1 class="text-4xl mt-[30px] font-bold text-center">
      {{ story.name }}
    </h1>
    <StoryblokComponent :blok="story.content" />
  </main>
</template>
