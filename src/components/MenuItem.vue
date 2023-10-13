<script setup>
import { ref } from 'vue'

const props = defineProps({
    image: String,
    name: String,
    description: String,
    price: String
})

const itemCount = ref(0)

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
  itemCount.value = currentOrder[props.name]
}
</script>

<template>
  <div class="dish-item">
    <img class="dish-image" :src="image" />
    <div class="dish-content">
      <div class="dish-content-top-mobile">
        <h2 class="dish-name-mobile heading">{{ name }}</h2>
        <p class="dish-price-mobile heading">$ {{ price }}</p>
      </div>
      <h2 class="dish-name heading">{{ name }}</h2>
      <p class="dish-description">{{ description }}</p>
      <p class="dish-price heading">$ {{ price }}</p>
      <div class="dish-btn">
        <button @click="order(), $emit('item-ordered')" type="button" class="dish-order-btn">Order</button>
        <button class="dish-count-btn" type="button">{{ itemCount }}</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.dish-item {
  min-width: 200px;
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

.dish-content-top-mobile {
  display: none;
}

.dish-name {
  margin: 0px;
}

.dish-price {
  margin: 0px;
}

.dish-btn {
  max-width: 100%;
}

.dish-order-btn, .dish-count-btn {
  border: none;
  background-color: var(--highlight);
  font-size: 16px;
  padding: 5px 15px;
  color: var(--background);
  margin-top: 10px;
  transition: color 0.2s, background-color 0.2s
}

.dish-order-btn {
  border-radius: 5px 0px 0px 5px;
  border-right: 2px solid var(--heading);
}

.dish-count-btn {
  border-radius: 0px 5px 5px 0px;
}

.dish-order-btn:hover, .dish-count-btn:hover {
  color: var(--highlight);
  background-color: var(--background);
}

.dish-order-btn:active {
  color: var(--text);
}

@media (max-width: 768px) {
  .dish-item {
    display: flex;
  }
  
  .dish-image {
    width: 200px;
    flex-grow: 0;
  }
}

@media (max-width: 480px) {
  .dish-content-top-mobile {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .dish-name, .dish-price {
    display: none;
  }

  .dish-name-mobile, .dish-price-mobile {
    margin: 0px;
  }

  .dish-image {
    width: calc(100% - 10px);
    height: 20px;
    flex: 0;
  }
  
  .dish-item {
    flex-direction: column;
  }
}
</style>
