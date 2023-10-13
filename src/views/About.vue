<script setup>
import Header from "/src/components/Header.vue";
import Footer from "/src/components/Footer.vue";

const orderLength = localStorage.getItem('orderLength')
</script>

<template>
    <Header :orderLength="orderLength" />
    <main>
        <img src="/ouzo.png">
        <h1 class="about-title heading">About Patroklos</h1>
        <p class="about-text">Some well-written, well-thought out thoughts on the important point that the title conveys Preferrably, these thoughts should give the reader an idea of the background of this restaurant, some of its values and its unique attributes.</p>
        <p class="about-text">It is important that the text be of sufficient length so that the about page does not look overly short. Even if there is nothing really important to say, the priority is to have two thick chunks of text to accompany the large images.</p>
        <p class="about-text">Greek food tastes great, you know. It originated from the meals Athenians used to eat in ancient times. During the Golden Age of athens, traditional Athenian cuisine was spread to all its fellow city-states which Athens controlled, or conquered.</p>
        <img src="/souvlaki.png">
        <p class="about-text">While Greek cuisine began very crudely, as Greece grew rich and powerful its chefs and foodies had more time to develop and perfect the various simple meals people were used to eating at this time. There was development of new breads, new meat-roasting methods, and many more such innovations.</p>
        <p class="about-text">This led to the development of many now classic Greek dishes, including Gyros, Kataifi and Souvlaki. There was. however, an exception to this pattern of purposeful culinary innovation. It was Ouzo.</p>
        <p class="about-text">Ouzo was the happy byproduct of an barrel of coconut milk freshly imported from Northern Africa, accidentally left uncovered during a downpour. This fact was not noticed for a few days, and when the watered-down coconut milk was discovered, it had fermented into a highly alchoholic and fragrant white, cloudy beverage.</p>
    </main>
    <Footer />
</template>

<style scoped>
main {
    padding: 0px min(300px, 20%) 50px;
}

img {
    width: calc(100% - 10px);
    height: 400px;
    border: 5px solid var(--highlight);
    object-fit: cover;
    margin-top: 50px;
}

@media (max-width: 768px) {
    main {
        padding: 0px 10% 10%;
    }
}
</style>