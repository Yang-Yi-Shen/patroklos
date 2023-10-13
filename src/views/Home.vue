<script setup>
import { ref } from 'vue'

import Header from "/src/components/Header.vue";
import MenuItem from "/src/components/MenuItem.vue";
import Footer from "/src/components/Footer.vue";

const orderLength = ref(0)
const orderMessage = ref(localStorage.getItem('order') || 'No items selected')

function orderItem() {
  orderMessage.value = localStorage.getItem('order')
  orderLength.value += 1
}
</script>

<template>
  <Header :orderLength="orderLength" />
  <main>
    <h1 class="main-dishes-title heading">Main Dishes</h1>
    <div class="dish-list">
      <MenuItem @item-ordered="orderItem" image="/gyros.png" name="Lamb Gyros" description="Lamp meat wrapped with thick Greek bread" price="6.99" />
      <MenuItem @item-ordered="orderItem" image="/moussaka.png" name="Moussaka" description="A Greek version of Italian Lasagna, using lamb meat" price="6.99" />
      <MenuItem @item-ordered="orderItem" image="/souvlaki.png" name="Souvlaki" description="Roasted meats on a skewer, accompanied by light herbs" price="4.20" />
    </div>
    <h1 class="additional-dishes-title heading">Additional Dishes</h1>
    <div class="dish-list">
      <MenuItem @item-ordered="orderItem" image="/ouzo.png" name="Ouzo" description="Dense alchoholic beverage made from grapes" price="6.99" />
      <MenuItem @item-ordered="orderItem" image="/kataifi.png" name="Kataifi" description="A thready, crunchy greek confection" price="4.20" />
      <MenuItem @item-ordered="orderItem" image="/yogurt.png" name="Greek Yogurt" description="Sour yogurt without artificial seasoning" price="4.20" />
    </div>
  </main>
  <div class="order">
    <a class="order-btn heading" :href="`mailto:mrshenyangyi@gmail.com?subject=Restaurant order&body=${orderMessage}%0D%0A%0D%0AWhile this is just an email with the order contents, you can see you this would translate to integration with an actual restaurant's ordering system.%0D%0AYou can replace the fake email with yours to have it sent to your inbox, if you wish.`">Place your order</a>
  </div>
  <div class="contact">
    <h1 class="contact-title heading">Contact Us</h1>
    <p class="contact-subtitle">Check out our social media accounts, or directly call us at 06-969-420</p>
    <div class="contact-list">
      <a class="contact-item" href="https://www.facebook.com/RickAstley/" target="_blank">
        <span class="contact-icon fa-brands fa-facebook-square"></span>
        <span class="contact-name">Facebook</span>
      </a>
      <a class="contact-item" href="https://www.instagram.com/officialrickastley/" target="_blank">
        <span class="contact-icon fa-brands fa-instagram"></span>
        <span class="contact-name">Instagram</span>
      </a>
      <a class="contact-item" href="https://twitter.com/rickastley?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor" target="_blank">
        <span class="contact-icon fa-brands fa-twitter"></span>
        <span class="contact-name">Twitter</span>
      </a>
    </div>
  </div>
  <Footer />
</template>

<style scoped>
main {
  padding: 50px 200px 50px;
}

.dish-list {
  display: flex;
  gap: 50px;
  margin-bottom: 50px;
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

.order {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 100px;
}

.order-btn {
  margin: 0px auto;
  padding: 10px 20px;
  font-size: 22px;
  border-radius: 5px;
  border: none;
  background-color: var(--heading);
  color: var(--background);
  transition: background-color 0.2s;
  text-decoration: none;
}

.order-btn:hover {
  background-color: var(--highlight);
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
  color: var(--heading);
  text-decoration: none;
  transition: color 0.2s;
}

.contact-item:hover {
  color: var(--background);
}

.contact-icon {
  font-size: 40px;
}
</style>
