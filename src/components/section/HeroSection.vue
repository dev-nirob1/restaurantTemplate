<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import HeroTitle from '../Elements/HeroTitle.vue';

</script>

<template>
    <section class="hero flex-center">
        <div class="content">
            <HeroTitle>Savor the Art of Dining</HeroTitle>
            <BaseParagraph>
                Where every dish tells a story, crafted with locally-sourced ingredients.
            </BaseParagraph>
            <div class="flex-center gap-1">
                <BaseButton class="bg-alternative">Reserve a Table</BaseButton>
                <BaseButton class="outline">Explore Menu</BaseButton>
            </div>
        </div>
    </section>
</template>
<style scoped>
.hero {
    min-height: 100vh;
    text-align: center;
    color: var(--white-color);
    background: linear-gradient(to bottom, rgb(from var(--primary-color) r g b / 60%), rgb(from var(--primary-color) r g b / 50%)), url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80') center / cover no-repeat fixed;
}

@media (min-width: 768px) {
    .hero .content {
        max-width: 80%;
    }

    .hero p {
        font-size: 1.25rem;
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