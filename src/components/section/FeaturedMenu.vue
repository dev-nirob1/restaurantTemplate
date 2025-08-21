<script setup>
import BaseTitle from '../Elements/BaseTitle.vue';
import MenuCard from '../Widget/MenuCard.vue';

const featuredMenu = [
  {
    name: 'Grilled Salmon',
    description: 'Fresh Atlantic salmon grilled to perfection with lemon butter.',
    price: 22.99,
    image: 'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=500&q=80'
  },
  {
    name: 'Spaghetti Carbonara',
    description: 'Classic Italian pasta with creamy sauce and crispy pancetta.',
    price: 18.50,
    image: 'https://images.unsplash.com/photo-1612548041350-853c0cd6e299?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
    name: 'Caesar Salad',
    description: 'Crisp romaine, creamy dressing, croutons, and parmesan.',
    price: 12.25,
    image: 'https://images.unsplash.com/photo-1580013759032-c96505e24c1f?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjR8fGNhZXNhciUyMHNhbGFkfGVufDB8fDB8fHww'
  },
  {
    name: 'Margherita Pizza',
    description: 'Stone-baked pizza with fresh mozzarella, tomato, and basil.',
    price: 15.00,
    image: 'https://images.unsplash.com/photo-1573821663912-6df460f9c684?q=80&w=774&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
        name: 'Chocolate Cake',
        description: 'Rich and moist dark chocolate cake with ganache.',
        price: 6.5,
        image: 'https://images.unsplash.com/photo-1626196874981-40349a369168?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  },
  {
    name: 'Strawberry Cheesecake',
        description: 'Creamy cheesecake with a fresh strawberry topping.',
        price: 7.0,
        image: 'https://images.unsplash.com/photo-1729542920554-411daacea77b?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
  }
];

</script>
<template>
  <section id="featured-menu" class="menu-section">
    <div class="container">
      <div class="text-center mb-2">
        <BaseTitle>Featured Menu</BaseTitle>
      </div>

      <div class="medium-2 large-3 gap-2">
        <MenuCard v-for="(menu, i) in featuredMenu" :key="i" :menu="menu" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.menu-section {
  padding: 3.75rem 0;
}
</style>
