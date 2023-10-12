<script setup>
defineProps({
    image: String,
    name: String,
    description: String,
    price: String
})
</script>

<template>
  <div class="dish-item">
    <img class="dish-image" :src="image" />
    <div class="dish-content">
      <h2 class="dish-name heading">{{ name }}</h2>
      <p class="dish-description">{{ description }}</p>
      <p class="dish-price heading">$ {{ price }}</p>
    </div>
  </div>
</template>

<style scoped>
.dish-item {
  background-color: var(--text);
  color: var(--background);
}

.dish-item .heading {
  color: var(--highlight);
}

.dish-image {
  width: calc(100% - 10px);
  object-fit: cover;
  border: 5px solid var(--highlight);
  flex: 1;
}

.dish-content {
  padding: 20px;
}

.dish-name {
  margin: 0px;
}

.dish-price {
  margin: 0px;
}
</style>
