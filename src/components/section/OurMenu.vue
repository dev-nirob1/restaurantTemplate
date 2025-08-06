<script setup>
import { computed, ref } from 'vue';
import MenuCard from '../Widget/MenuCard.vue';
import ListItem from '../Elements/ListItem.vue';
import BaseButton from '../Elements/BaseButton.vue';

const selectedId = ref(1)

const ourMenu = ref([
    {
        "id": 1,
        "title": "Restaurant Solution",
        "image": "https://zems.uk/uploads/media/1747030497.gif",
        "alt": "Restaurant management system",
        "subtitle": "A complete restaurant solution",
        "description": "Scale your restaurant business efficiently with our end-to-end management system designed to optimize every aspect of your operations including:",
        "features": [
            "Table management & reservations",
            "Integrated POS with kitchen display",
            "Inventory tracking & supplier management",
            "Staff scheduling & performance analytics",
            "Customer loyalty programs"
        ]
    },
    {
        "id": 2,
        "title": "Grocery POS",
        "image": "https://zems.uk/uploads/media/1744799107.gif",
        "alt": "Grocery point of sale system",
        "subtitle": "Modern grocery store management",
        "description": "Modernize every aspect of your grocery store management - from checkout to inventory - with our all-in-one POS solution featuring:",
        "features": [
            "Barcode scanning & inventory management",
            "Fresh produce weighing integration",
            "Supplier ordering automation",
            "Expiry date tracking",
            "Mobile payment integration"
        ]
    },
    {
        "id": 3,
        "title": "Real Estate App",
        "image": "https://zems.uk/uploads/media/1744799207.gif",
        "alt": "Real estate application",
        "subtitle": "Comprehensive property management",
        "description": "Revolutionize your real estate business with our powerful digital platform, designed to streamline operations and boost sales through innovative features like:",
        "features": [
            "Property listing management",
            "Virtual tour integration",
            "Client CRM system",
            "Automated document generation",
            "Market analytics dashboard"
        ]
    }
])
const currentTab = (id) => {
    selectedId.value = id;
}
const menu = computed(() => {
    return ourMenu.value.find(data => data.id === selectedId.value)
})

</script>

<template>
    <section class="our-menu">
        <div class="container">

            <div class="tab-panel">
                <ul>
                    <ListItem v-for="(tab, i) in ourMenu" :key="i">
                        <BaseButton :class="{ 'bg-primary': selectedId === tab.id }" @click="currentTab(tab.id)">{{
                            tab.title }}
                        </BaseButton>
                    </ListItem>
                </ul>
            </div>

            <div class="medium-2 gap-2 align-center">
                <MenuCard v-for="item in menu" :key="item.id" :menu="menu"/>
            </div>
        </div>
    </section>
</template>

<style scoped>
.our-menu {
    padding: 3.75rem 0;
}

.tab-panel ul {
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 3rem 0;
}

.tab-panel ul li .btn {
    padding: .75rem 1rem;
    margin: 0;
}

.our-menu .app-image {
    height: 100%;
    width: 100%;
}

.our-menu .app-image img {
    height: 100%;
    width: 100%;
    object-fit: cover;
}

.our-menu .btn {
    padding: .75rem 1rem;
}

@media (min-width: 768px) {
    .our-menu .btn {
        font-size: 1.15rem;
        margin-top: .5rem;
    }

    .tab-panel ul li .btn {
        font-size: 1.15rem;
        padding: 1.15rem 2rem;
    }
}
</style>