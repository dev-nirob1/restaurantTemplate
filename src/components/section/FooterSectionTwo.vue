<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Brand Column -->
      <div class="footer-brand">
        <h3 class="logo">
          <span class="gold">Epicurean</span>Elegance
        </h3>
        <p class="tagline">Where culinary art meets unforgettable experiences.</p>
        <div class="social-links">
          <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
          <a href="#" class="social-icon"><i class="fab fa-facebook-f"></i></a>
          <a href="#" class="social-icon"><i class="fab fa-tripadvisor"></i></a>
        </div>
      </div>

      <!-- Quick Links -->
      <div class="footer-links">
        <h4 class="footer-title">Quick Links</h4>
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/menu">Seasonal Menu</router-link></li>
          <li><router-link to="/about">Our Chefs</router-link></li>
          <li><router-link to="/gallery">Food Gallery</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </div>

      <!-- Contact Info -->
      <div class="footer-contact">
        <h4 class="footer-title">Visit Us</h4>
        <ul>
          <li><i class="fas fa-map-marker-alt"></i> 123 Gourmet Avenue, Foodie City</li>
          <li><i class="fas fa-phone"></i> +1 (555) 123-4567</li>
          <li><i class="fas fa-envelope"></i> reservations@epicureanelegance.com</li>
          <li><i class="fas fa-clock"></i> Tue-Sun: 5:30 PM - 11:00 PM</li>
        </ul>
      </div>

    </div>

    <!-- Copyright -->
    <div class="copyright">
      <p>&copy; {{ new Date().getFullYear() }} Epicurean Elegance. All rights reserved.</p>
      <div class="legal-links">
        <router-link to="/privacy">Privacy Policy</router-link>
        <router-link to="/terms">Terms of Service</router-link>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    subscribe() {
      alert(`Thank you for subscribing with ${this.email}!`);
      this.email = '';
    }
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

/* Footer Base Styles */
.footer {
  background-color: var(--navy);
  color: var(--cream);
  padding: 4rem 0 0;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
}

/* Brand Column */
.footer-brand {
  margin-bottom: 2rem;
}

.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.8rem;
  margin-bottom: 1rem;
  color: var(--cream);
}

.gold {
  color: var(--gold);
}

.tagline {
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-icon {
  color: var(--cream);
  background: rgba(248, 244, 233, 0.1);
  width: 36px;
  height: 36px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s;
}

.social-icon:hover {
  background: var(--gold);
  color: var(--navy);
  transform: translateY(-3px);
}

/* Links Section */
.footer-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.3rem;
  margin-bottom: 1.5rem;
  color: var(--gold);
  position: relative;
  display: inline-block;
}

.footer-title::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 50px;
  height: 2px;
  background: var(--gold);
}

.footer-links ul,
.footer-contact ul {
  list-style: none;
  padding: 0;
}

.footer-links li,
.footer-contact li {
  margin-bottom: 0.8rem;
}

.footer-links a,
.footer-contact a {
  color: var(--cream);
  text-decoration: none;
  transition: color 0.3s;
}

.footer-links a:hover {
  color: var(--gold);
}

.footer-contact i {
  color: var(--gold);
  width: 20px;
  margin-right: 10px;
}

/* Newsletter */
.newsletter-form {
  display: flex;
  margin-top: 1rem;
}

.newsletter-form input {
  flex: 1;
  padding: 0.8rem;
  border: none;
  border-radius: 4px 0 0 4px;
  font-family: 'Montserrat', sans-serif;
}

.subscribe-btn {
  background: var(--burgundy);
  color: var(--cream);
  border: none;
  padding: 0 1.2rem;
  border-radius: 0 4px 4px 0;
  cursor: pointer;
  transition: all 0.3s;
}

.subscribe-btn:hover {
  background: var(--gold);
  color: var(--navy);
}

/* Copyright */
.copyright {
  background: rgba(0, 0, 0, 0.2);
  padding: 1.5rem 0;
  margin-top: 3rem;
  text-align: center;
  font-size: 0.9rem;
}

.legal-links {
  margin-top: 0.5rem;
}

.legal-links a {
  color: var(--cream);
  margin: 0 10px;
  text-decoration: none;
  transition: color 0.3s;
}

.legal-links a:hover {
  color: var(--gold);
}

/* Responsive */
@media (max-width: 768px) {
  .footer-container {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .footer-brand,
  .footer-links,
  .footer-contact,
  .footer-newsletter {
    text-align: center;
  }
  
  .footer-title::after {
    left: 50%;
    transform: translateX(-50%);
  }
  
  .social-links {
    justify-content: center;
  }
}
</style>