<template>
  <div
    v-editable="blok"
    class="container mx-auto mt-[40px] mb-[40px] w-2/5 text-center"
  >
    <div v-html="resolvedRichText" class="prose"></div>
  </div>
</template>

<script setup>
const props = defineProps({ blok: Object });

const resolvedRichText = computed(() => renderRichText(props.blok.content));
</script>
