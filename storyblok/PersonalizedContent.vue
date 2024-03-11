<template>
  <div v-editable="blok">
    <StoryblokComponent
      v-for="blok in variant.content"
      :key="blok._uid"
      :blok="blok"
    />
  </div>
</template>

<script setup>
const props = defineProps({ blok: Object });

const userType = useUserType();
const variant = props.blok.variants.find((v) => v.user_type === userType);
</script>
