<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseImage from '../Elements/BaseImage.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import BaseTitle from '../Elements/BaseTitle.vue';

</script>

<template>
    <section class="special-section">
        <div class="container">
            <div class="medium-2 gap-2 align-center">
                <div class="image-container order-2 medium-order-1">
                    <BaseImage image="https://images.unsplash.com/photo-1600891964599-f61ba0e24092"
                        alt="Special Dish" />
                </div>
                <div class="content order-1 medium-order-2">
                    <BaseTitle class="text-secondary">Today’s Special</BaseTitle>
                    <BaseTitle>Grilled Salmon Delight</BaseTitle>
                    <BaseParagraph>
                        Fresh Atlantic salmon grilled to perfection, served with herb butter,
                        lemon zest, and seasonal vegetables.
                    </BaseParagraph>
                    <BaseParagraph class="price">$24.99</BaseParagraph>
                    <BaseButton>Order Now</BaseButton>
                    <BaseParagraph class="chef-note">~ Recommended by Chef Antonio</BaseParagraph>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.special-section {
    background-color: var(--light-color);
    padding: 3.75rem 0;
}

.special-section .image-container {
    width: 100%;
    height: auto;
}
.special-section .image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 1.5rem;
    border: 3px solid var(--secondary-color);
}

.special-section p {
    margin: .75rem 0;
}

.special-section .price {
    margin-top: 0;
    font-size: 1.4rem;
    font-weight: bold;
    color: var(--secondary-color);
}

.special-section .btn {
    width: fit-content;
    background-color: var(--secondary-color);
    color: var(--primary-color);
    padding: .75rem 1rem;
    border-radius: 2rem;
    margin: 0;
}

.special-section .chef-note {
    font-style: italic;
    font-size: 0.9rem;
    margin-top: .75rem;
}
@media (min-width: 768px) {
    .special-section .btn {
        padding: .8rem 2rem;
    }
}
</style>
