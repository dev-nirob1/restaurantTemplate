<script setup>
import { computed, ref } from 'vue';
import MenuCard from '../Widget/MenuCard.vue';
import ListItem from '../Elements/ListItem.vue';
import BaseButton from '../Elements/BaseButton.vue';
import BaseTitle from '../Elements/BaseTitle.vue';

const categoryList = ref(['Starters', 'Main Course', 'Desserts', 'Drinks'])
const selectedCategory = ref('Starters')

const ourMenu = ref([
    {
        id: 1,
        category: 'Starters',
        name: 'Garlic Bread',
        description: 'Toasted bread with garlic, herbs, and olive oil.',
        price: 5.99,
        image: 'https://images.unsplash.com/photo-1556008531-57e6eefc7be4?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGdhcmxpYyUyMGJyZWFkfGVufDB8fDB8fHww'
    },
    {
        id: 2,
        category: 'Starters',
        name: 'Caesar Salad',
        description: 'Crisp romaine, creamy dressing, croutons, and parmesan.',
        price: 7.49,
        image: 'https://images.unsplash.com/photo-1580013759032-c96505e24c1f?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjR8fGNhZXNhciUyMHNhbGFkfGVufDB8fDB8fHww'
    },

    {
        id: 3,
        category: 'Main Course',
        name: 'Grilled Salmon',
        description: 'Fresh Atlantic salmon grilled to perfection with lemon butter.',
        price: 22.99,
        image: 'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=500&q=80'
    },
    {
        id: 4,
        category: 'Main Course',
        name: 'Spaghetti Carbonara',
        description: 'Classic Italian pasta with creamy sauce and crispy pancetta.',
        price: 18.5,
        image: 'https://images.unsplash.com/photo-1612548041350-853c0cd6e299?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'

    },
    {
        id: 5,
        category: 'Main Course',
        name: 'Margherita Pizza',
        description: 'Stone-baked pizza with fresh mozzarella, tomato, and basil.',
        price: 15.0,
        image: 'https://images.unsplash.com/photo-1573821663912-6df460f9c684?q=80&w=774&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },

    {
        id: 6,
        category: 'Desserts',
        name: 'Chocolate Cake',
        description: 'Rich and moist dark chocolate cake with ganache.',
        price: 6.5,
        image: 'https://images.unsplash.com/photo-1626196874981-40349a369168?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },
    {
        id: 7,
        category: 'Desserts',
        name: 'Strawberry Cheesecake',
        description: 'Creamy cheesecake with a fresh strawberry topping.',
        price: 7.0,
        image: 'https://images.unsplash.com/photo-1729542920554-411daacea77b?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    },

    {
        id: 8,
        category: 'Drinks',
        name: 'Lemonade',
        description: 'Freshly squeezed lemonade with mint.',
        price: 3.99,
        image: 'https://images.pexels.com/photos/10684607/pexels-photo-10684607.jpeg?_gl=1*6b9pkm*_ga*OTAzOTgwMTguMTczNzAwNTI1OA..*_ga_8JE65Q40S6*czE3NTU3NjY3NTYkbzI2JGcxJHQxNzU1NzY3MjM1JGo1NSRsMCRoMA..'
    },
    {
        id: 9,
        category: 'Drinks',
        name: 'Iced Coffee',
        description: 'Chilled coffee with cream and ice.',
        price: 4.25,
        image: 'https://images.unsplash.com/photo-1625242662167-9ba73d268139?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
    }
])

const currentTab = (category) => {
    selectedCategory.value = category;
}

const menu = computed(() => {
    return ourMenu.value.filter(data => data.category === selectedCategory.value)
})

</script>

<template>
    <section id="menu" class="our-menu">
        <div class="container">
            <BaseTitle class="text-center">Explore Our Food Category</BaseTitle>
            <div class="tab-panel">
                <ul class="flex-center">
                    <ListItem v-for="(tab, i) in categoryList" :key="i">
                        <BaseButton :class="{ 'active': selectedCategory === tab }" @click="currentTab(tab)">{{ tab }}
                        </BaseButton>
                    </ListItem>
                </ul>
            </div>

            <div class="medium-2 large-3 gap-2 align-center">
                <MenuCard v-for="item in menu" :key="item.id" :menu="item" />
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
    list-style: none;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 3rem 0;
}

.tab-panel ul li .btn {
    padding: .75rem 1rem;
    margin: 0;
    color: var(--primary-color);
    background-color: var(--white-color);
}

.tab-panel ul li .btn.active {
    background-color: var(--alternative-color);
    color: var(--white-color);
    border-color: var(--alternative-color);
}

.tab-panel ul li .btn:hover {
    background: var(--alternative-color);
    color: var(--white-color);
    border-color: var(--alternative-color)
}

@media (min-width: 768px) {
    .tab-panel ul li .btn {
        padding: 1rem 1.5rem;
    }
}
</style>