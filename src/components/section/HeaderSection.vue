<template>
  <nav :class="{ 'scrolled': isScrolled }" class="navbar">
    <div class="container">
      <!-- Logo -->
      <router-link to="/" class="logo">
        <span class="gold">Epicurean</span>Elegance
      </router-link>

      <!-- Mobile Toggle -->
      <button @click="toggleMenu" class="menu-toggle">
        <span class="bar" :class="{ 'rotate-45': isOpen }"></span>
        <span class="bar" :class="{ 'opacity-0': isOpen }"></span>
        <span class="bar" :class="{ 'rotate--45': isOpen }"></span>
      </button>

      <!-- Desktop Menu -->
      <ul class="nav-links" :class="{ 'active': isOpen }">
        <li><router-link to="/" @click="closeMenu">Home</router-link></li>
        <li><router-link to="/menu" @click="closeMenu">Menu</router-link></li>
        <li><router-link to="/about" @click="closeMenu">Our Story</router-link></li>
        <li><router-link to="/reservations" @click="closeMenu" class="">Reservations</router-link></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      isScrolled: false
    }
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen
    },
    closeMenu() {
      this.isOpen = false
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped>
/* Color Variables */
:root {
  --navy: #2A3A5E;
  --gold: #D4AF37;
  --cream: #F8F4E9;
  --sage: #A4B494;
  --burgundy: #6D2E46;
}

/* Base Styles */
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  padding: 1.5rem 0;
  transition: all 0.3s ease;
  z-index: 1000;
  color: var(--white-color)
}

.navbar.scrolled {
  padding: 1rem 0;
  background: rgba(42, 58, 94, 0.98);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Logo */
.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--cream);
  text-decoration: none;
}

.gold {
  color: var(--gold);
}

/* Navigation Links */
.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links li a {
  font-family: 'Montserrat', sans-serif;
  color: var(--cream);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s;
  position: relative;
}

.nav-links li a:hover {
  color: var(--gold);
}

.nav-links li a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--gold);
  transition: width 0.3s;
}

.nav-links li a:hover::after {
  width: 100%;
}

.cta-button {
  background: var(--burgundy);
  padding: 0.6rem 1.5rem;
  border-radius: 30px;
  transition: all 0.3s;
}

.cta-button:hover {
  background: var(--gold);
  color: var(--navy) !important;
  transform: translateY(-2px);
}

/* Mobile Menu */
.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 21px;
  background: transparent;
  border: none;
  cursor: pointer;
  z-index: 1001;
}

.bar {
  height: 3px;
  width: 100%;
  background: var(--cream);
  transition: all 0.3s ease;
}

.rotate-45 {
  transform: translateY(9px) rotate(45deg);
}

.rotate--45 {
  transform: translateY(-9px) rotate(-45deg);
}

.opacity-0 {
  opacity: 0;
}

/* Responsive Design */
@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 0;
    right: -100%;
    width: 70%;
    height: 100vh;
    background: var(--navy);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: right 0.5s ease;
    box-shadow: -5px 0 15px rgba(0, 0, 0, 0.2);
  }

  .nav-links.active {
    right: 0;
  }

  .nav-links li {
    margin: 1.5rem 0;
  }
}
</style>