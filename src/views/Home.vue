<template>
<section class="p-4">
  <h4 class="h4 text-center">Vue 3</h4>

  <input
    v-model="name"
    class="form-control">

  <div class="my-text">
    {{ name }}
  </div>

  <button @click="incrementSize">
    incrementSize
  </button>
</section>
</template>

<script setup>
const { ref, computed } = require('vue');


const name = ref('Christian')
const size = ref(10)

function incrementSize () {
  size.value++
}

const computedSize = computed(() => size.value + 'px')

export {
  name,
  incrementSize,
  computedSize
}

/**
 * multiple nodes
 * <script setup>
 */
</script>

<style vars="{ computedSize }">
.my-text {
 font-size: var(--computedSize);
}
</style>
