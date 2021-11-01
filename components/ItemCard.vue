<template>
  <nuxt-link
    class="h-120 w-72 rounded shadow-lg mx-auto border border-purple-100"
    :to="`/products/${slug}`"
  >
      <div class="h-72 border-b-2 border-purple-100 relative">
          <div style="display: block; overflow: hidden; position: absolute; inset: 0px; box-sizing: border-box; margin: 0px;">
            <img
              alt="test-text"
              :src="image"
              class="transform duration-500 ease-in-out hover:scale-110"
              style="position: absolute; inset: 0px; box-sizing: border-box; padding: 0px; border: none; margin: auto; display: block; width: 0px; height: 0px; min-width: 100%; max-width: 100%; min-height: 100%; max-height: 100%;"
            >
          </div>
      </div>
      <div class="h-48 relative">
          <div class="font-primary text-purple-600 text-2xl pt-4 px-4 font-semibold">{{ title }}</div>
          <div class="text-lg text-gray-600 p-4 font-primary font-light">{{ description }}</div>
          <div class="bg-purple-100 text-purple-600 font-primary font-medium text-base absolute bottom-0 right-0 mb-4 pl-8 pr-4 pb-1 pt-2 rounded-tl-sm triangle">
            <span class="text-lg">
              {{ formattedPrice }}
            </span>
          </div>
      </div>
  </nuxt-link>
</template>

<script>
import currencies from '~/utils/currencies.json'

export default {
  props: {
    title: {
      type: String,
      default: 'Nome do produto',
    },

    description: {
      type: String,
      default: 'Descrição'
    },

    price: {
      type: Number,
      default: 0
    },

    currency: {
      type: String,
      default: 'USD'
    },

    image: {
      type: String,
      default: 'https://lh3.googleusercontent.com/proxy/5o1nw15I8h9K5p1PANCe_AmI2qA9jgu-e7EqvxiNW_94ecCCA5I09hxOyp6ePqSBjKtfwW0LsaSe8s6Xc337EdNAhNci5S4SavWs14Zj9J4OyqXvc8Vxdu3ARVcUTQZCpFQeZn4iztliHrq2bIEVAJYhGa85TkaPdJy0NfPhAcDWxCI57-9j'
    },

    slug: {
      type: String,
      required: true
    }

  },

  data() {
    return {
      currencies,
    }
  },

  computed: {
    formattedPrice() {
      if (this.price > 0) {
        return this.currencies[this.currency] + this.price;
      }

      return 'Grátis'
    }
  }
}
</script>

<style scoped>
  .triangle::before {
    content: "";
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    border: 1em solid transparent;
    border-left-color: #fff;
  }
</style>
