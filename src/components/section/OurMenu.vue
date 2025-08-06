<template>
  <section class="category-menu-section">
    <h2 class="section-title">Explore Our Menu</h2>

    <!-- Tabs -->
    <div class="tabs">
      <button
        v-for="cat in categories"
        :key="cat"
        @click="activeCategory = cat"
        :class="['tab', { active: activeCategory === cat }]"
      >
        {{ cat }}
      </button>
    </div>

    <!-- Menu Items -->
    <div class="medium-2">
      <div
        v-for="item in filteredMenu"
        :key="item.name"
        class="menu-card"
      >
        <img :src="item.image" :alt="item.name" />
        <h3>{{ item.name }}</h3>
        <p>{{ item.description }}</p>
        <span class="price">${{ item.price }}</span>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeCategory = ref('Starters')

const categories = ['Starters', 'Main Course', 'Desserts', 'Drinks']

const menuItems = [
  {
    name: 'Garlic Bread',
    category: 'Starters',
    image: 'https://via.placeholder.com/150',
    description: 'Toasted bread with garlic and herbs.',
    price: 5.99,
  },
  {
    name: 'Grilled Chicken',
    category: 'Main Course',
    image: 'https://via.placeholder.com/150',
    description: 'Juicy grilled chicken with seasonal vegetables.',
    price: 12.99,
  },
  {
    name: 'Chocolate Cake',
    category: 'Desserts',
    image: 'https://via.placeholder.com/150',
    description: 'Rich and moist dark chocolate cake.',
    price: 6.5,
  },
  {
    name: 'Lemonade',
    category: 'Drinks',
    image: 'https://via.placeholder.com/150',
    description: 'Freshly squeezed lemonade with mint.',
    price: 3.99,
  },
  // Add more items if needed
]

const filteredMenu = computed(() =>
  menuItems.filter(item => item.category === activeCategory.value)
)
</script>

<style scoped>
.category-menu-section {
  padding: 4rem 1rem;
  background-color: #fff7f3;
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  color: #2c2c2c;
}

.tabs {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
  margin-bottom: 2rem;
}

.tab {
  padding: 0.5rem 1.5rem;
  border: 2px solid #6b1e1e;
  background-color: transparent;
  color: #6b1e1e;
  cursor: pointer;
  font-weight: bold;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.tab.active,
.tab:hover {
  background-color: #6b1e1e;
  color: white;
}

.menu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
}

.menu-card {
  background: white;
  padding: 1rem;
  border-radius: 16px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease;
}

.menu-card:hover {
  transform: translateY(-5px);
}

.menu-card img {
  width: 100%;
  border-radius: 12px;
  object-fit: cover;
}

.menu-card h3 {
  font-size: 1.2rem;
  margin: 0.75rem 0 0.25rem;
  color: #333;
}

.menu-card p {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 0.5rem;
}

.price {
  font-weight: bold;
  color: #6b1e1e;
}
</style>
