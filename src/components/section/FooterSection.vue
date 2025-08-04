<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-about">
        <h2 class="footer-logo">Resto<span>Prime</span></h2>
        <p>Delivering exquisite dining experiences with passion and flavor.</p>
      </div>

      <div class="footer-links">
        <h3>Quick Links</h3>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Menu</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Reservations</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>

      <div class="footer-contact">
        <h3>Contact Us</h3>
        <p>123 Gourmet Blvd,<br />Food City, FC 45678</p>
        <p>Phone: (123) 456-7890</p>
        <p>Email: info@restoprime.com</p>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2025 RestoPrime. All rights reserved.</p>
    </div>
  </footer>
</template>

<style scoped>
:root {
  --primary-color: #0B1D2F;
  --secondary-color: #D9C59A;
  --accent-color: #8B1E1E;
}

.footer {
  background-color: var(--primary-color);
  color: var(--secondary-color);
  padding: 3rem 2rem 2rem;
  font-family: 'Inter', sans-serif;
  border-top: 1px solid rgba(217, 197, 154, 0.15);
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 3rem;
  flex-wrap: wrap;
  justify-content: space-between;
}

.footer-logo {
  font-family: 'Playfair Display', serif;
  font-size: 2rem;
  font-weight: 700;
  color: var(--secondary-color);
}

.footer-logo span {
  color: var(--accent-color);
}

.footer-about p {
  max-width: 320px;
  margin-top: 0.5rem;
  line-height: 1.6;
  color: var(--secondary-color);
  opacity: 0.85;
}

.footer-links,
.footer-contact {
  min-width: 180px;
}

.footer-links h3,
.footer-contact h3 {
  margin-bottom: 1rem;
  font-weight: 600;
  color: var(--secondary-color);
}

.footer-links ul {
  list-style: none;
  padding: 0;
}

.footer-links ul li {
  margin-bottom: 0.7rem;
}

.footer-links ul li a {
  color: var(--secondary-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links ul li a:hover {
  color: var(--accent-color);
}

.footer-contact p {
  margin-bottom: 0.7rem;
  line-height: 1.5;
  opacity: 0.85;
}

.footer-bottom {
  margin-top: 2rem;
  text-align: center;
  font-size: 0.9rem;
  color: var(--secondary-color);
  opacity: 0.7;
}

@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
    gap: 2rem;
    text-align: center;
  }

  .footer-about p {
    margin: 0 auto;
  }
}
</style>
