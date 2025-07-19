<template>
  <section class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <h1>Discover Your Style</h1>
        <p>Explore the latest fashion trends and update your wardrobe today. Exclusive deals just for you!</p>
        <button>Shop Now</button>
      </div>
      <div class="hero-image">
        <img
          src="https://cdn.pixabay.com/photo/2016/03/27/21/30/people-1284418_1280.jpg"
          alt="Fashion Hero"
          loading="lazy"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
:root {
  --primary: #985913;
  --secondary: #eac8a4;
  --accent: #bc8889;
  --highlight: #00adda;
}

.hero {
  background: var(--secondary);
  padding: 2rem 1rem;
}

.hero-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

.hero-text {
  text-align: center;
  color: var(--primary);
}

.hero-text h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.hero-text p {
  font-size: 1rem;
  margin-bottom: 1.5rem;
  color: var(--accent);
}

.hero-text button {
  background-color: var(--highlight);
  color: white;
  border: none;
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  cursor: pointer;
  border-radius: 8px;
  transition: background-color 0.3s ease;
}

.hero-text button:hover {
  background-color: var(--primary);
}

.hero-image img {
  max-width: 100%;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
}

@media (min-width: 768px) {
  .hero-content {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .hero-text {
    flex: 1;
    text-align: left;
  }

  .hero-text h1 {
    font-size: 3rem;
  }

  .hero-text p {
    font-size: 1.2rem;
  }

  .hero-image {
    flex: 1;
    padding-left: 2rem;
  }
}
</style>
