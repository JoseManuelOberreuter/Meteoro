<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-main">
        <div class="footer-logo">
          <img 
            src="@/assets/Sin Fondo_IMAGOTIPO.png" 
            alt="METEORO Logo" 
            class="footer-logo-image"
            @click="scrollToTop"
          >
        </div>
        
        <div class="footer-newsletter">
          <h3>SUSCRÍBETE</h3>
          <p>Suscríbete y disfruta de material exclusivo, novedades, descuentos y más</p>
          <form class="newsletter-form" @submit.prevent="handleSubmit">
            <input 
              type="email" 
              placeholder="Tu correo electrónico" 
              class="newsletter-input" 
              v-model="email"
              required
            >
            <button type="submit" class="newsletter-button">SUSCRIBIRSE</button>
          </form>
        </div>
        
        <div class="footer-social">
          <a href="https://www.youtube.com/@SelloMeteoro" target="_blank" class="social-icon">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
            </svg>
          </a>
          <a href="https://www.instagram.com/sellometeoro/" target="_blank" class="social-icon">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
          </a>
          <a href="https://www.tiktok.com/@sellometeoro" target="_blank" class="social-icon">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.04-1.36 1.75-.21.51-.15 1.07-.14 1.61.24 1.64 1.82 3.02 3.5 2.87 1.12-.01 2.19-.66 2.77-1.61.19-.33.4-.67.41-1.06.1-1.79.06-3.57.07-5.36.01-4.03-.01-8.05.02-12.07z"/>
            </svg>
          </a>
          <a href="https://sellometeoro.bandcamp.com/" target="_blank" class="social-icon">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M0 18.75l7.437-13.5H24l-7.438 13.5H0z"/>
            </svg>
          </a>
        </div>
      </div>
      
      <p>&copy; 2025 SELLO METEORO.</p>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'

// Reactive data
const email = ref('')

// Methods
const handleSubmit = () => {
  // Handle newsletter subscription
  console.log('Newsletter subscription:', email.value)
  // Reset form
  email.value = ''
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}
</script>

<style scoped>
/* Footer */
.footer {
  background: var(--black);
  padding: 50px 0;
}

.footer-content {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
  text-align: center;
}

.footer-main {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  gap: 60px;
  margin-bottom: 40px;
}

.footer-logo {
  display: flex;
  align-items: flex-end;
  cursor: pointer;
  margin-bottom: -10px;
}

.footer-logo-image {
  height: 7rem;
  width: auto;
  transition: all 0.3s ease;
  filter: brightness(0) invert(1);
}

.footer-logo-image:hover {
  transform: scale(1.1);
}

.footer-newsletter {
  flex: 1;
  text-align: left;
}

.footer-newsletter h3 {
  color: var(--white);
  font-size: 1.8rem;
  font-weight: 900;
  margin-bottom: 15px;
}

.footer-newsletter p {
  color: var(--white);
  opacity: 0.8;
  font-size: 1rem;
  margin-bottom: 25px;
  line-height: 1.5;
}

.newsletter-form {
  display: flex;
  gap: 15px;
  max-width: 550px;
}

.newsletter-input {
  flex: 1;
  min-width: 300px;
  padding: 12px 20px;
  border: none;
  border-radius: 5px;
  background: var(--white);
  color: var(--black);
  font-size: 1rem;
  outline: none;
  transition: all 0.3s ease;
}

.newsletter-input:focus {
  box-shadow: 0 0 0 3px rgba(249, 255, 69, 0.3);
}

.newsletter-input::placeholder {
  color: rgba(26, 26, 26, 0.6);
}

.newsletter-button {
  background: var(--neon-yellow);
  color: var(--black);
  border: none;
  padding: 12px 25px;
  border-radius: 5px;
  font-weight: 700;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  white-space: nowrap;
}

.newsletter-button:hover {
  background: var(--white);
  transform: translateY(-2px);
}

.footer-social {
  display: flex;
  justify-content: flex-end;
  gap: 20px;
}

.social-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-icon svg {
  width: 20px;
  height: 20px;
  transition: all 0.3s ease;
}

.social-icon {
  background: var(--white);
  color: var(--black);
}

.social-icon:hover {
  background: var(--neon-yellow);
  color: var(--black);
  transform: translateY(-3px);
}

.footer-content p {
  color: var(--white);
  font-weight: 700;
  opacity: 0.8;
}

/* Responsive Design */
/* Tablet */
@media (max-width: 1024px) {
  .footer-content {
    padding: 0 30px;
  }
  
  .footer-main {
    gap: 40px;
  }
  
  .footer-logo-image {
    height: 7rem;
  }
  
  .footer-newsletter h3 {
    font-size: 1.6rem;
  }
  
  .newsletter-form {
    max-width: 450px;
  }
}

/* Mobile Large */
@media (max-width: 768px) {
  .footer {
    padding: 40px 0 30px;
  }
  
  .footer-content {
    padding: 0 20px;
  }
  
  .footer-main {
    flex-direction: column;
    gap: 35px;
    text-align: center;
    margin-bottom: 30px;
    align-items: center;
  }
  
  .footer-logo {
    justify-content: center;
    align-items: center;
    margin-bottom: 0;
  }

  .footer-logo-image {
    height: 6rem;
  }

  .footer-newsletter {
    text-align: center;
  }
  
  .footer-newsletter h3 {
    font-size: 1.5rem;
    margin-bottom: 12px;
  }
  
  .footer-newsletter p {
    font-size: 0.9rem;
    margin-bottom: 20px;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }
  
  .newsletter-form {
    flex-direction: column;
    gap: 12px;
    max-width: 100%;
    margin: 0 auto;
  }
  
  .newsletter-input {
    padding: 12px 18px;
    min-width: unset;
    width: 100%;
    font-size: 0.95rem;
  }
  
  .newsletter-button {
    padding: 12px 25px;
    font-size: 0.85rem;
    font-weight: 800;
  }
  
  .footer-social {
    justify-content: center;
    gap: 18px;
  }
  
  .social-icon {
    width: 42px;
    height: 42px;
  }
  
  .social-icon svg {
    width: 20px;
    height: 20px;
  }
  
  .footer-content > p {
    font-size: 0.85rem;
    margin-top: 20px;
  }
}

/* Mobile Medium */
@media (max-width: 480px) {
  .footer {
    padding: 30px 0 25px;
  }
  
  .footer-content {
    padding: 0 15px;
  }
  
  .footer-main {
    gap: 25px;
    margin-bottom: 25px;
    align-items: center;
  }
  
  .footer-logo {
    justify-content: center;
    align-items: center;
  }
  
  .footer-social {
    justify-content: center;
  }
  
  .footer-logo-image {
    height: 5rem;
  }
  
  .footer-newsletter h3 {
    font-size: 1.3rem;
    margin-bottom: 10px;
  }
  
  .footer-newsletter p {
    font-size: 0.85rem;
    margin-bottom: 18px;
    line-height: 1.4;
  }
  
  .newsletter-form {
    gap: 10px;
  }
  
  .newsletter-input {
    padding: 10px 15px;
    font-size: 0.9rem;
  }
  
  .newsletter-button {
    padding: 10px 20px;
    font-size: 0.8rem;
  }
  
  .footer-social {
    gap: 15px;
  }
  
  .social-icon {
    width: 38px;
    height: 38px;
  }
  
  .social-icon svg {
    width: 18px;
    height: 18px;
  }
  
  .footer-content > p {
    font-size: 0.8rem;
    margin-top: 15px;
  }
}

/* Mobile Small */
@media (max-width: 360px) {
  .footer {
    padding: 25px 0 20px;
  }
  
  .footer-content {
    padding: 0 12px;
  }
  
  .footer-main {
    gap: 20px;
    margin-bottom: 20px;
    align-items: center;
  }
  
  .footer-logo {
    justify-content: center;
    align-items: center;
  }
  
  .footer-social {
    justify-content: center;
  }
  
  .footer-logo-image {
    height: 4rem;
  }
  
  .footer-newsletter h3 {
    font-size: 1.2rem;
  }
  
  .footer-newsletter p {
    font-size: 0.8rem;
    margin-bottom: 15px;
  }
  
  .newsletter-input {
    padding: 9px 12px;
    font-size: 0.85rem;
  }
  
  .newsletter-button {
    padding: 9px 18px;
    font-size: 0.75rem;
  }
  
  .footer-social {
    gap: 12px;
  }
  
  .social-icon {
    width: 35px;
    height: 35px;
  }
  
  .social-icon svg {
    width: 16px;
    height: 16px;
  }
  
  .footer-content > p {
    font-size: 0.75rem;
    margin-top: 12px;
  }
}
</style> 