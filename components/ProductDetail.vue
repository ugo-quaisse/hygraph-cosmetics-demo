<script setup>
defineProps(["product"]);
</script>
<template>
  <section class="bg-light product-detail pb-12">
    <div class="grid grid-cols-2">
      <img
        v-for="image in product.images"
        :src="`https://res.cloudinary.com/dwfcofnrd/image/fetch/c_fill,ar_1:1,q_auto,f_auto/${image.url}`"
        :alt="image.alt"
        class="aspect-[1/1] object-cover"
      />
    </div>
    <div class="flex flex-col md:flex-row mx-4 lg:mx-16 mb-12">
      <div class="bg-secondary p-8 md:-mt-12 flex-1 w-full md:w-2/4">
        <h1>
          <span class="block text-primary font-bold font-title text-6xl"
            >your</span
          ><span
            class="block text-dark font-bold font-title text-6xl ml-8 -mt-2"
            >{{ product.name }}</span
          >
        </h1>
      </div>
      <div class="bg-tertiary p-8 md:-mt-12 w-full md:w-2/4">
        <p class="text-5xl font-bold font-title mb-4">${{ product.price }}</p>
        <a href="#" class="cta" target="_blank">add to cart</a>
      </div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mx-8 md:mx-16">
      <div class="pr-2">
        <h2 class="text-3xl font-bold font-title mb-4">product description</h2>
        <article v-html="product.description" />
      </div>
      <div class="pl-2">
        <h3 class="text-3xl font-bold font-title mb-4">ingredients</h3>
        <article v-html="product.ingredients" />
      </div>
    </div>
  </section>
</template>
