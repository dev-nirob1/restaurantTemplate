<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseImage from '../Elements/BaseImage.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import HeroTitle from '../Elements/HeroTitle.vue';

</script>

<!-- AboutUs.vue -->
<template>
    <section class="about-us">
        <div class="container">
            <div class="medium-2 gap-2 align-center">
                <div class="content">
                    <HeroTitle>Our Food Philosophy</HeroTitle>
                    <BaseParagraph>
                        We see our customers as invited guests to a party, and we are the hosts. It’s our job every day
                        to make every important aspect of the customer experience a little bit better.
                    </BaseParagraph>
                    <BaseButton>Learn More</BaseButton>
                </div>
                <div class="images">
                    <BaseImage image="https://images.unsplash.com/photo-1600891964599-f61ba0e24092" alt="image" />
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.about-us {
    padding: 3.75rem 0;
    color: var(--white-color);
    background: linear-gradient(to right, rgb(from var(--primary-color)r g b / 60%), rgb(from var(--primary-color) r g b / 60%)), url('https://images.unsplash.com/photo-1600891964599-f61ba0e24092') center / cover no-repeat;
}

.about-us .btn {
    padding: .75rem 1rem;
    border-radius: 2rem;
    color: var(--white-color);
    background-color: var(--alternative-color);
    border-color: var(--alternative-color);
}

.about-us .images {
    width: 100%;
    height: auto;
}

.about-us .images img {
    height: 100%;
    width: 100%;
    object-fit: cover;
}
@media (min-width: 768px){
.about-us .btn {
padding: .8rem 2rem;
}
}
</style>
