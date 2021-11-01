<template>
  <div class="mx-auto max-w-6xl">
    <WelcomeText />
    <GridItems>
      <ItemCard
        :slot="product.featured ? 'featured' : undefined"
        v-for="(product, i) in products"
        :key="i"
        :price="product.price"
        :title="product.title"
        :description="product.description"
        :image="product.image"
        :currency="product.currency"
        :slug="product.slug"
      />
    </GridItems>
  </div>
</template>

<script>
import products from '~/data.json'

export default {
  data(){
    return{
      products
    }
  }
}
</script>
