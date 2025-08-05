<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import SubTitle from '../Elements/SubTitle.vue';
import BaseImage from '../Elements/BaseImage.vue';

defineProps({
    menu: {
        type: Object
    }
})
</script>

<template>
    <div class="menu-card">
        <BaseParagraph class="price">$ {{ menu.price }}</BaseParagraph>
        <div class="image">
            <BaseImage :image="menu.image" alt="project image" />
        </div>
        <div class="p-1">
            <SubTitle>{{ menu.name }}</SubTitle>
            <BaseParagraph>{{ menu.description.substring(0, 60) }}...
            </BaseParagraph>
        </div>
    </div>
</template>

<style scoped>
.menu-card {
    box-shadow: var(--box-shadow);
    cursor: pointer;
    position: relative;
    border-radius: 1rem;
}
.menu-card .price{
    position: absolute;
    right: 0;
    top: 0;
    padding: .75rem 2rem;
    font-size: 1.25rem;
    margin: 0;
    border-top-right-radius: 1rem;
    color: var(--white-color);
    background-color: var(--alternative-color);
    z-index: 1;
}

.menu-card p {
    margin: .5rem 0;
}

.menu-card .image {
    position: relative;
    overflow: hidden;
    height: 220px;
    width: auto;
    border-radius: 1rem 1rem 0 0;
}

.menu-card .image img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: all .5s ease-in-out;
}

.menu-card .image:hover img {
    transform: scale(1.1);
}
</style>