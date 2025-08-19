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
        image: 'https://images.unsplash.com/photo-1621996346565-08cb32b2d9fa?auto=format&fit=crop&w=500&q=80'
    },
    {
        id: 2,
        category: 'Starters',
        name: 'Caesar Salad',
        description: 'Crisp romaine, creamy dressing, croutons, and parmesan.',
        price: 7.49,
        image: 'https://images.unsplash.com/photo-1604908177796-050f404dd76b?auto=format&fit=crop&w=500&q=80'
    },

    {
        id: 3,
        category: 'Main Course',
        name: 'Grilled Salmon',
        description: 'Fresh Atlantic salmon grilled to perfection with lemon butter.',
        price: 22.99,
        image: 'https://images.unsplash.com/photo-1661260652741-65340f04f2ff?q=80&w=1470&auto=format&fit=crop'
    },
    {
        id: 4,
        category: 'Main Course',
        name: 'Spaghetti Carbonara',
        description: 'Classic Italian pasta with creamy sauce and crispy pancetta.',
        price: 18.5,
        image: 'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=500&q=80'
    },
    {
        id: 5,
        category: 'Main Course',
        name: 'Margherita Pizza',
        description: 'Stone-baked pizza with fresh mozzarella, tomato, and basil.',
        price: 15.0,
        image: 'https://images.unsplash.com/photo-1601924582975-4be52b1eb4e7?auto=format&fit=crop&w=500&q=80'
    },

    {
        id: 6,
        category: 'Desserts',
        name: 'Chocolate Cake',
        description: 'Rich and moist dark chocolate cake with ganache.',
        price: 6.5,
        image: 'https://images.unsplash.com/photo-1601979031925-082d6919d1fd?auto=format&fit=crop&w=500&q=80'
    },
    {
        id: 7,
        category: 'Desserts',
        name: 'Strawberry Cheesecake',
        description: 'Creamy cheesecake with a fresh strawberry topping.',
        price: 7.0,
        image: 'https://images.unsplash.com/photo-1612197393831-f3ce2c2fdfae?auto=format&fit=crop&w=500&q=80'
    },

    {
        id: 8,
        category: 'Drinks',
        name: 'Lemonade',
        description: 'Freshly squeezed lemonade with mint.',
        price: 3.99,
        image: 'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=500&q=80'
    },
    {
        id: 9,
        category: 'Drinks',
        name: 'Iced Coffee',
        description: 'Chilled coffee with cream and ice.',
        price: 4.25,
        image: 'https://images.unsplash.com/photo-1598515214213-46e571e29cbe?auto=format&fit=crop&w=500&q=80'
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
    <section class="our-menu">
        <div class="container">
            <BaseTitle class="text-center">Explore Our Food Category</BaseTitle>
            <div class="tab-panel">
                <ul>
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
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 3rem 0;
}

.tab-panel ul li .btn {
    padding: .75rem 1rem;
    margin: 0;
    border-radius: 1.9rem;
    color: var(--primary-color);
    background-color: var(--white-color);
}

.tab-panel ul li .btn.active {
    background-color: var(--alternative-color);
    color: var(--white-color);
    border-color: var(--alternative-color);
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

@media (min-width: 768px) {
    .tab-panel ul li .btn {
        padding: 1rem 1.5rem;
    }
}
</style>