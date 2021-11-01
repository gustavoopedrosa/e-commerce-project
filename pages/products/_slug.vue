<template>
  <div class="min-h-screen py-12 sm:pt-20">
    <div class="flex flex-col justify-center items-center md:flex-row md:items-start space-y-8 md:space-y-0 md:space-x-4 lg:space-x-8 max-w-6xl w-11/12 mx-auto">
      <div class="w-full md:w-1/2 max-w-md border border-palette-lighter bg-white rounded shadow-lg">
        <div class="relative h-96">
          <div style="display: block; overflow: hidden; position: absolute; inset: 0px; box-sizing: border-box; margin: 0px;">
            <img
              alt="test-text"
              :src="product.image"
              class="transform duration-500 ease-in-out hover:scale-105"
              style="position: absolute; inset: 0px; box-sizing: border-box; padding: 0px; border: none; margin: auto; display: block; width: 0px; height: 0px; min-width: 100%; max-width: 100%; min-height: 100%; max-height: 100%;"
            >
          </div>
        </div>
        <div class="relative flex border-t border-palette-lighter">
          <ProductImageArrow/>
          <div class="flex space-x-1 w-full overflow-auto border-t border-palette-lighter" style="scroll-behavior: smooth;">
            <ProductImageButton/>
            <ProductImageButton/>
          </div>
          <ProductImageArrow direction="right"/>
        </div>
      </div>
      <div class="flex flex-col justify-between h-full w-full md:w-1/2 max-w-xs mx-auto space-y-4 min-h-128">
        <Back/>
        <div class=" font-primary">
          <h1 class="leading-relaxed font-extrabold text-3xl text-purple-700 py-2 sm:py-4">
            {{ product.title }}
          </h1>
          <p class="font-medium text-lg">
            {{ product.description }}
          </p>
          <div class="text-xl text-purple-700 font-medium py-4 px-1">
            {{ formattedPrice }}
            <span class="text-2xl">
              {{ product.price }}
            </span>
          </div>
        </div>
        <div class="w-full">
          <ProductInputs/>
          <AddToCart/>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import products from '~/data.json'
import currencies from '~/utils/currencies.json'

export default {
  data(){
    return{
      product: products.find(product => product.slug === this.$route.params.slug)
    }
  },

  computed: {
    formattedPrice() {
      if (this.product.price > 0) {
        return currencies[this.product.currency]
      }

      return 'Grátis'
    }
  }
}
</script>
