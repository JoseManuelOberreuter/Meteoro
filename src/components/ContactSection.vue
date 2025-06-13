<template>
  <section id="contacto" class="contact-section">
    <div class="section-container">
      <h2 class="section-title">CONECTA CON NOSOTROS</h2>
      <div class="contact-grid">
        <div class="contact-info">
          <h3>¿TIENES EL SONIDO QUE BUSCAMOS?</h3>
          <p>Envíanos tu demo y únete a la revolución sonora.</p>
          <div class="contact-methods">
            <a href="mailto:demos@Meteoro.com" class="contact-method">
              <span>DEMOS</span>
              <span>demos@Meteoro.com</span>
            </a>
            <a href="mailto:booking@Meteoro.com" class="contact-method">
              <span>BOOKING</span>
              <span>booking@Meteoro.com</span>
            </a>
            <a href="mailto:press@Meteoro.com" class="contact-method">
              <span>PRENSA</span>
              <span>press@Meteoro.com</span>
            </a>
          </div>
        </div>
        <div class="social-links">
          <h3>SÍGUENOS</h3>
          <div class="social-grid">
            <a href="#" class="social-link instagram">INSTAGRAM</a>
            <a href="#" class="social-link spotify">SPOTIFY</a>
            <a href="#" class="social-link youtube">YOUTUBE</a>
            <a href="#" class="social-link twitter">TWITTER</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// This component doesn't need any JavaScript logic
</script>

<style scoped>
/* Section Styles */
.section-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
}

.section-title {
  font-size: clamp(3rem, 6vw, 6rem);
  font-weight: 900;
  text-align: center;
  margin-bottom: 80px;
  letter-spacing: -1px;
  color: var(--black);
}

/* Contact Section */
.contact-section {
  padding: 120px 0;
  background: var(--white);
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
}

.contact-info h3 {
  font-size: 2rem;
  font-weight: 900;
  margin-bottom: 20px;
  color: var(--black);
}

.contact-info p {
  font-size: 1.2rem;
  margin-bottom: 40px;
  opacity: 0.7;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-method {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background: var(--black);
  color: var(--white);
  text-decoration: none;
  transition: all 0.3s ease;
}

.contact-method:hover {
  background: var(--neon-yellow);
  color: var(--black);
  transform: translateX(10px);
}

.social-links h3 {
  font-size: 2rem;
  font-weight: 900;
  margin-bottom: 40px;
  color: var(--black);
}

.social-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 30px 20px;
  text-decoration: none;
  font-weight: 900;
  font-size: 1.1rem;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.social-link.instagram {
  background: var(--saturated-red);
  color: var(--white);
}

.social-link.spotify {
  background: var(--electric-blue);
  color: var(--white);
}

.social-link.youtube {
  background: var(--black);
  color: var(--white);
}

.social-link.twitter {
  background: var(--neon-yellow);
  color: var(--black);
}

.social-link:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .social-grid {
    grid-template-columns: 1fr;
  }
}
</style> 