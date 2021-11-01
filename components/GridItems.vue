<template>
  <div>
    <h2 class="text-2xl">Itens em destaque</h2>
    <div class="py-12 max-w-6xl mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-x-4 gap-y-8">
        <slot name="featured" />
     </div>

    <h2 class="text-2xl">Novos itens</h2>
    <div class="py-12 max-w-6xl mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-x-4 gap-y-8">
        <slot />
     </div>
  </div>
</template>
