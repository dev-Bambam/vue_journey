<script setup>
import { ref, computed } from 'vue'

// Initial price
const price = ref(100)

// Discount percentage
const discount = ref(0)

// Computed property to automatically calculate discounted price
const discountedPrice = computed(() => {
  return price.value * (1 - discount.value / 100)
})
</script>

<template>
  <div class="about">
    <div>
      <h2>Price: ${{ price }}</h2>
      <label for="discount">Discount: {{ discount }}%</label>
      <input type="range" id="discount" v-model="discount" min="0" max="100" />
      <h3>Discounted Price: ${{ discountedPrice }}</h3>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
