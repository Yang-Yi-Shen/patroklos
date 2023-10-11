<script setup>
import Header from "/src/components/Header.vue";
import MenuItem from "/src/components/MenuItem.vue";
import Footer from "/src/components/Footer.vue";
</script>

<template>
  <Header />
  <main>
    <h1 class="main-dishes-title heading">Main Dishes</h1>
    <div class="dish-list">
      <div class="dish-item">
        <img class="dish-image" src="/gyros.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
      <div class="dish-item">
        <img class="dish-image" src="/moussaka.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
      <div class="dish-item">
        <img class="dish-image" src="/souvlaki.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
    </div>
    <h1 class="additional-dishes-title heading">Additional Dishes</h1>
    <div class="dish-list">
      <div class="dish-item">
        <img class="dish-image" src="/ouzo.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
      <div class="dish-item">
        <img class="dish-image" src="/kataifi.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
      <div class="dish-item">
        <img class="dish-image" src="/yogurt.png" />
        <div class="dish-content">
            <h2 class="dish-name heading">Dish Name</h2>
            <p class="dish-description">Very succint and informative description of dish</p>
            <p class="dish-price heading">$ 6.99</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
    padding: 50px 200px;
}

.dish-list {
    display: flex;
    gap: 50px;
}

.dish-item {
    background-color: var(--text);
    color: var(--background)
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
