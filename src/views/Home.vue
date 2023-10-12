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
  <div class="contact">
    <h1 class="contact-title heading">Contact Us</h1>
    <p class="contact-subtitle">Check out our social media accounts, or directly call us at 06-969-420</p>
    <div class="contact-list">
      <div class="contact-item">
        <span class="contact-icon fa-brands fa-facebook-square"></span>
        <span class="contact-name">Facebook</span>
      </div>
      <div class="contact-item">
        <span class="contact-icon fa-brands fa-instagram"></span>
        <span class="contact-name">Instagram</span>
      </div>
      <div class="contact-item">
        <span class="contact-icon fa-brands fa-twitter"></span>
        <span class="contact-name">Twitter</span>
      </div>
    </div>
  </div>
  <Footer />
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

/* contact section */
.contact {
  text-align: center;
  background-color: var(--contrast);
  color: var(--heading);
  padding: 50px 0px;
}

.contact-title {
  color: var(--heading);
  margin: 0px;
}

.contact-list {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 50px;
  margin-top: 50px;
}

.contact-item {
  display: flex;
  flex-direction: column;
}

.contact-icon {
  font-size: 40px;
}
</style>
