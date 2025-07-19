<template>
  <footer class="site-footer">
    <div class="footer-container">
      <!-- Footer Top Section -->
      <div class="footer-top">
        <!-- Newsletter Section -->
        <div class="footer-newsletter">
          <h3 class="footer-heading">Stay Updated</h3>
          <p class="footer-text">Subscribe for exclusive offers and updates</p>
          <form class="newsletter-form">
            <input 
              type="email" 
              placeholder="Your email address" 
              class="newsletter-input"
              required
            >
            <button type="submit" class="newsletter-button">
              Subscribe <i class="fas fa-arrow-right"></i>
            </button>
          </form>
        </div>

        <!-- Quick Links -->
        <div class="footer-links">
          <div class="links-column">
            <h3 class="footer-heading">Shop</h3>
            <ul class="links-list">
              <li><a href="#new-arrivals" class="footer-link">New Arrivals</a></li>
              <li><a href="#best-sellers" class="footer-link">Best Sellers</a></li>
              <li><a href="#sale" class="footer-link">Sale Items</a></li>
              <li><a href="#gift-cards" class="footer-link">Gift Cards</a></li>
            </ul>
          </div>
          
          <div class="links-column">
            <h3 class="footer-heading">Customer Service</h3>
            <ul class="links-list">
              <li><a href="#faq" class="footer-link">FAQs</a></li>
              <li><a href="#shipping" class="footer-link">Shipping Info</a></li>
              <li><a href="#returns" class="footer-link">Returns Policy</a></li>
              <li><a href="#contact" class="footer-link">Contact Us</a></li>
            </ul>
          </div>
          
          <div class="links-column">
            <h3 class="footer-heading">Company</h3>
            <ul class="links-list">
              <li><a href="#about" class="footer-link">About Us</a></li>
              <li><a href="#blog" class="footer-link">Our Blog</a></li>
              <li><a href="#careers" class="footer-link">Careers</a></li>
              <li><a href="#privacy" class="footer-link">Privacy Policy</a></li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Footer Bottom Section -->
      <div class="footer-bottom">
        <div class="footer-bottom-content">
          <!-- Social Media Links -->
          <div class="social-links">
            <a href="#facebook" class="social-link" aria-label="Facebook">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a href="#instagram" class="social-link" aria-label="Instagram">
              <i class="fab fa-instagram"></i>
            </a>
            <a href="#twitter" class="social-link" aria-label="Twitter">
              <i class="fab fa-twitter"></i>
            </a>
            <a href="#pinterest" class="social-link" aria-label="Pinterest">
              <i class="fab fa-pinterest-p"></i>
            </a>
          </div>

          <!-- Payment Methods -->
          <div class="payment-methods">
            <i class="fab fa-cc-visa payment-icon"></i>
            <i class="fab fa-cc-mastercard payment-icon"></i>
            <i class="fab fa-cc-amex payment-icon"></i>
            <i class="fab fa-cc-paypal payment-icon"></i>
            <i class="fab fa-cc-apple-pay payment-icon"></i>
          </div>

          <!-- Copyright -->
          <div class="copyright">
            &copy; {{ new Date().getFullYear() }} YourStoreName. All rights reserved.
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>


<style scoped>
/* Color Variables */
:root {
  --color-primary: #985913;
  --color-light: #EAC8A4;
  --color-muted: #BC8889;
  --color-accent: #00ADDA;
  --color-text: #333333;
  --color-text-light: #777777;
  --color-bg: #ffffff;
  --color-bg-dark: #2a2a2a;
  --color-border: #e0e0e0;
}

/* Base Footer Styles */
.site-footer {
  background-color: var(--color-bg-dark);
  color: var(--color-light);
  padding: 3rem 0 0;
  font-size: 0.9rem;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Footer Top Section */
.footer-top {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid var(--color-muted);
}

.footer-heading {
  color: var(--color-light);
  font-size: 1.1rem;
  margin-bottom: 1rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.footer-text {
  color: var(--color-muted);
  margin-bottom: 1rem;
  line-height: 1.5;
}

/* Newsletter Form */
.newsletter-form {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.newsletter-input {
  padding: 0.8rem;
  border: 1px solid var(--color-muted);
  border-radius: 4px;
  background-color: rgba(255, 255, 255, 0.1);
  color: var(--color-light);
}

.newsletter-input::placeholder {
  color: var(--color-muted);
}

.newsletter-button {
  padding: 0.8rem;
  background-color: var(--color-primary);
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  transition: background-color 0.3s ease;
}

.newsletter-button:hover {
  background-color: var(--color-accent);
}

/* Footer Links */
.footer-links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 2rem;
}

.links-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-link {
  color: var(--color-muted);
  text-decoration: none;
  display: block;
  padding: 0.5rem 0;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: var(--color-light);
}

/* Footer Bottom Section */
.footer-bottom {
  padding: 1.5rem 0;
}

.footer-bottom-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  color: var(--color-light);
  background-color: rgba(255, 255, 255, 0.1);
  width: 36px;
  height: 36px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.3s ease;
}

.social-link:hover {
  background-color: var(--color-primary);
}

.payment-methods {
  display: flex;
  gap: 0.8rem;
  flex-wrap: wrap;
  justify-content: center;
}

.payment-icon {
  font-size: 1.8rem;
  color: var(--color-light);
  opacity: 0.8;
  transition: opacity 0.3s ease;
}

.payment-icon:hover {
  opacity: 1;
}

.copyright {
  color: var(--color-muted);
  text-align: center;
  font-size: 0.8rem;
}

/* Responsive Styles */
@media (min-width: 768px) {
  .footer-top {
    grid-template-columns: 1fr 2fr;
  }
  
  .footer-bottom-content {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
}

@media (min-width: 992px) {
  .footer-top {
    grid-template-columns: 1fr 3fr;
  }
  
  .footer-links {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>