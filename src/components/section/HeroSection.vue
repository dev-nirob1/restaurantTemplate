<template>
  <section class="hero">
    <!-- Background Image with Overlay -->
    <div class="hero-background">
      <img 
        src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" 
        alt="Elegant restaurant interior"
        class="hero-image"
      />
      <div class="overlay"></div>
    </div>

    <!-- Hero Content -->
    <div class="hero-content">
      <h1 class="hero-title">Savor the <span class="gold">Art</span> of Dining</h1>
      <p class="hero-subtitle">Where every dish tells a story, crafted with locally-sourced ingredients.</p>
      <div class="hero-buttons">
        <button class="btn-primary bg-secondary">Reserve a Table</button>
        <button class="btn-secondary">Explore Menu</button>
      </div>
    </div>

    <!-- Scrolling Indicator -->
    <div class="scroll-indicator" @click="scrollToContent">
      <span class="chevron"></span>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    scrollToContent() {
      window.scrollBy({ top: window.innerHeight - 100, behavior: 'smooth' });
    }
  }
};
</script>

<style scoped>

/* Hero Section */
.hero {
  position: relative;
  height: 100vh;
  min-height: 600px;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--white-color);
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.hero-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    to bottom,
    rgba(42, 58, 94, 0.56) 0%,
    rgba(42, 58, 94, 0.618) 100%
  );
}

.hero-content {
  text-align: center;
  max-width: 800px;
  padding: 0 2rem;
  animation: fadeInUp 1s ease-out;
}

.hero-title {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.gold {
  color: var(--gold);
}

.hero-subtitle {
  font-size: 1.2rem;
  margin-bottom: 2.5rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.btn-primary {
  background: var(--alternative-color);
  color: var(--cream);
  border: none;
  padding: 0.8rem 2rem;
  font-size: 1rem;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
}

.btn-primary:hover {
  background: var(--gold);
  color: var(--navy);
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.btn-secondary {
  background: transparent;
  color: var(--cream);
  border: 2px solid var(--secondary-color);
  padding: 0.8rem 2rem;
  font-size: 1rem;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
}

.btn-secondary:hover {
  background: rgba(248, 244, 233, 0.1);
  border-color: var(--secondary-color);
  color: var(--gold);
  transform: translateY(-3px);
}

/* Scroll Indicator */
.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  cursor: pointer;
  animation: bounce 2s infinite;
}

.chevron {
  display: block;
  width: 20px;
  height: 20px;
  border-bottom: 2px solid var(--gold);
  border-right: 2px solid var(--gold);
  transform: rotate(45deg);
  margin: -10px;
}

/* Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0) translateX(-50%);
  }
  40% {
    transform: translateY(-20px) translateX(-50%);
  }
  60% {
    transform: translateY(-10px) translateX(-50%);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .hero-buttons {
    flex-direction: column;
    gap: 0.5rem;
  }

  .btn-primary, .btn-secondary {
    width: 100%;
    max-width: 250px;
    margin: 0 auto;
  }
}
</style>