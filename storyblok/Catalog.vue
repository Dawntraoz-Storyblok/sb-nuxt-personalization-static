<template>
  <div v-editable="blok" class="container mx-auto px-[25px] mt-20">
    <div class="grid md:grid-cols-4 sm:grid-cols-1 gap-10">
      <div
        v-for="product in products"
        :key="product.uuid"
        class="flex flex-col"
      >
        <img
          :src="`${product.content.image.filename}/m/500x300/smart/`"
          :alt="product.name"
          class="h-[250px] w-full object-cover object-top rounded-lg"
        />
        <h3 class="mt-6 text-xl">{{ product.name }}</h3>
        <span>&euro; {{ product.content.price }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({ blok: Object });

const products = (useProducts() || []).filter(
  (p) => blok.category === "" || p.content.category === blok.category
);
</script>
