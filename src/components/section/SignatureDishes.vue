<script setup>
const dishes = [
  {
    name: "Truffle Risotto",
    ingredients: ["Arborio rice", "black truffle", "parmesan", "white wine"],
    price: "$32",
    image: "https://images.unsplash.com/photo-1630918237419-c5f7730a1e30"
  },
  {
    name: "Seared Scallops",
    ingredients: ["Fresh scallops", "cauliflower purée", "crispy prosciutto", "micro greens"],
    price: "$38",
    image: "https://images.unsplash.com/photo-1551248429-4091aa4e74a9"
  },
  {
    name: "Wagyu Beef",
    ingredients: ["A5 Wagyu", "truffle mashed potatoes", "roasted vegetables", "red wine reduction"],
    price: "$89",
    image: "https://images.unsplash.com/photo-1600891964599-f61ba0e24092"
  },
  {
    name: "Lobster Ravioli",
    ingredients: ["Homemade pasta", "lobster filling", "saffron cream sauce", "cherry tomatoes"],
    price: "$42",
    image: "https://images.unsplash.com/photo-1625944525803-d510d5a4f7ac"
  },
  {
    name: "Chocolate Soufflé",
    ingredients: ["Valrhona chocolate", "farm eggs", "vanilla bean", "crème anglaise"],
    price: "$18",
    image: "https://images.unsplash.com/photo-1563805042-7684c019e1cb"
  }
]
</script>

<template>
  <section class="signature-dishes">
    <div class="section-header">
      <h2><span class="gold">Chef's</span> Specialties</h2>
      <p>Seasonal creations that define our culinary philosophy</p>
    </div>
    
    <div class="dish-grid">
      <div 
        v-for="(dish, index) in dishes" 
        :key="index" 
        class="dish-card"
        @mouseenter="hoverIndex = index"
        @mouseleave="hoverIndex = -1"
      >
        <img 
          :src="dish.image" 
          :alt="dish.name" 
          class="dish-image"
          loading="lazy"
        >
        <div class="dish-overlay" :class="{ 'active': hoverIndex === index }">
          <h3>{{ dish.name }}</h3>
          <p class="ingredients">{{ dish.ingredients.join(', ') }}</p>
          <p class="price">{{ dish.price }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style >
/* Color Variables */
:root {
  --navy: #2A3A5E;
  --gold: #D4AF37;
  --cream: #F8F4E9;
  --sage: #A4B494;
  --burgundy: #6D2E46;
}

.signature-dishes {
  padding: 4rem 2rem;
  background-color: var(--cream);
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  font-family: 'Playfair Display', serif;
  font-size: 2.5rem;
  color: var(--navy);
  margin-bottom: 0.5rem;
}

.gold {
  color: var(--gold);
}

.section-header p {
  font-family: 'Montserrat', sans-serif;
  color: var(--navy);
  opacity: 0.8;
}

.dish-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.dish-card {
  border-radius: 8px;
  overflow: hidden;
  position: relative;
  transition: all 0.3s ease;
  aspect-ratio: 1/1.2;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.dish-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.dish-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.dish-card:hover .dish-image {
  transform: scale(1.05);
}

.dish-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(42, 58, 94, 0.9) 0%, transparent 100%);
  color: white;
  padding: 1.5rem;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}

.dish-overlay.active {
  transform: translateY(0);
}

.dish-overlay h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.ingredients {
  font-family: 'Montserrat', sans-serif;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
  opacity: 0.9;
}

.price {
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  color: var(--gold);
}

@media (max-width: 768px) {
  .section-header h2 {
    font-size: 2rem;
  }
  
  .dish-grid {
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  }
  
  .dish-overlay {
    transform: translateY(0);
    background: rgba(42, 58, 94, 0.7);
  }
}
</style>