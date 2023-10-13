<script setup>
const props = defineProps({
    image: String,
    name: String,
    description: String,
    price: String
})

function order() {
  const currentOrder = JSON.parse(localStorage.getItem('order'))
  if (currentOrder[props.name]) {
    currentOrder[props.name] += 1;
    console.log(currentOrder)
    localStorage.setItem('order', JSON.stringify(currentOrder))
  } else {
    currentOrder[props.name] = 1;
    console.log(currentOrder)
    localStorage.setItem('order', JSON.stringify(currentOrder))
  }
}
</script>

<template>
  <div class="dish-item">
    <img class="dish-image" :src="image" />
    <div class="dish-content">
      <h2 class="dish-name heading">{{ name }}</h2>
      <p class="dish-description">{{ description }}</p>
      <p class="dish-price heading">$ {{ price }}</p>
      <button @click="order" type="button" class="dish-btn">Order</button>
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

.dish-btn {
  border: none;
  background-color: var(--highlight);
  border-radius: 5px;
  font-size: 16px;
  padding: 5px 15px;
  color: var(--background);
  margin-top: 10px;
  transition: color 0.2s, background-color 0.2s
}

.dish-btn:hover {
  color: var(--highlight);
  background-color: var(--background);
}

.dish-btn:active {
  color: var(--text);
}
</style>
