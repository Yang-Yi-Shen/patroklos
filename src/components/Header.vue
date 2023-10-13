<script setup>
import { RouterLink } from 'vue-router'

defineProps({
    orderLength: Number
})
</script>

<template>
    <header>
        <RouterLink class="logo-link" to="/">
            <img class="logo" src="/logo.png">
        </RouterLink>
        <nav class="menu">
            <RouterLink class="menu-about" to="/about">About</RouterLink>
            <p class="menu-cart">
                <span class="menu-cart-icon fa-solid fa-cart-shopping"></span>
                <span class="menu-cart-badge">{{ orderLength }}</span>
            </p>
        </nav>
    </header>
</template>

<style scoped>    
header {
    background-color: var(--heading);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0px min(200px, 15%);
}

.logo {
    height: 24px;
}

nav {
    display: flex;
    align-items: center;
    gap: 30px;
    font-size: 18px;
}

.menu-about {
    text-decoration: none;
    color: var(--background);
}

.menu-cart {
    color: var(--background);
}

.menu-about:hover, .menu-cart:hover {
    color: #bfc3ba;
}

.menu-cart-badge {
    height: 12px;
    width: 12px;
    position: relative;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 1px;
    border-radius: 50%;
    background-color: red;
    font-size: 10px;
    bottom: 10px;
}

@media (max-width: 768px) {
    header {
        flex-direction: column;
        padding: 20px 0px;
        gap: 20px;
    }

    nav {
        width: 100%;
        justify-content: space-evenly;
    }

    .menu-about, .menu-cart {
        margin: 0px;
    }
}
</style>