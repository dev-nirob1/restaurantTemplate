<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import HeroTitle from '../Elements/HeroTitle.vue';

</script>

<template>
    <section class="hero">
        <div class="content">
            <HeroTitle>Savor the Art of Dining</HeroTitle>
            <BaseParagraph>
                Where every dish tells a story, crafted with locally-sourced ingredients.
            </BaseParagraph>
            <div class="flex justify-center gap-1">
                <BaseButton class="bg-alternative">Reserve a Table</BaseButton>
                <BaseButton class="outline">Explore Menu</BaseButton>
            </div>
        </div>
    </section>
</template>
<style scoped>
.hero {
    font-family: 'Montserrat', sans-serif;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: var(--white-color);
    background: linear-gradient(to bottom, rgb(from var(--primary-color) r g b / 60%), rgb(from var(--primary-color) r g b / 50%)), url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80') center / cover no-repeat;
}

.hero p {
    font-size: 1.25rem;
}

/* buttons styles  */
.hero .btn {
    color: var(--white-color);
    border-radius: 2rem;
    padding: .75rem 1rem;
}

.hero .btn.outline {
    border-color: var(--secondary-color);
    color: var(--white-color);
}

.hero .btn.outline:hover {
    background: rgb(from var(--primary-color) r g b / 30%);
    transform: translateY(-.25rem);
    border-color: var(--secondary-color);
    color: var(--secondary-color);
}

.hero .btn.bg-alternative {
    border-color: var(--alternative-color);
}

.hero .btn.bg-alternative:hover {
    transform: translateY(-.25rem);
    color: var(--primary-color);
    border-color: var(--secondary-color);
    background-color: var(--secondary-color);
}

@media (min-width: 768px) {
    .hero .content {
        max-width: 80%;
    }

    .hero .btn {
        padding: .8rem 2rem;
    }
}

@media (min-width: 992px) {
    .hero .content {
        max-width: 60%;
    }

    .hero .hero-title {
        font-size: 4rem;
    }
}
</style>