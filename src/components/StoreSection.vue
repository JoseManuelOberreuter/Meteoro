<template>
  <section id="tienda" class="store-section">
    <div class="section-container">
      <div class="coming-soon-content">
        <h2 class="section-title">TIENDA METEORO</h2>
        <div class="coming-soon-box">
          <div class="construction-icon">👩🏻‍💻🧑🏻‍💻</div>
          <h3>PRÓXIMAMENTE</h3>
          <p>Estamos preparando algo especial para ti.<br>Merchandising exclusivo y ediciones limitadas.</p>
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
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 900;
  text-align: left;
  margin-bottom: 40px;
  letter-spacing: -1px;
  color: var(--black);
  border-bottom: 5px solid #000000;
  display: inline-block;
}

/* Store Section */
.store-section {
  padding: 80px 0 200px 0 ;
  background: #F5F5F0;
}

.coming-soon-content {
  text-align: left;
}

.store-section .section-title {
  color: #1A1A1A;
  margin-bottom: 40px;
}

.coming-soon-box {
  background: var(--white);
  border-radius: 10px;
  padding: 40px 30px;
  max-width: 500px;
  margin: 40px auto 0 auto;
  text-align: center;
}

.construction-icon {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.coming-soon-box h3 {
  font-size: 1.8rem;
  font-weight: 900;
  color: var(--black);
  margin-bottom: 15px;
}

.coming-soon-box p {
  font-size: 1rem;
  color: var(--black);
  opacity: 0.7;
  line-height: 1.5;
  margin-bottom: 25px;
}

.notify-button {
  background: var(--neon-yellow);
  color: var(--black);
  border: none;
  padding: 12px 25px;
  font-size: 0.9rem;
  font-weight: 700;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
}

.notify-button:hover {
  background: var(--white);
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .coming-soon-box {
    padding: 30px 20px;
    margin: 0 20px;
  }
  
  .coming-soon-box h3 {
    font-size: 1.5rem;
  }
}
</style> 