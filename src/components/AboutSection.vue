<template>
  <section id="sobre" class="about-section">
    <div class="section-container">
      <div class="about-content">
        <div class="about-text">
          <h2 class="section-title">SOBRE NOSOTRXS</h2>
          <p>
            Meteoro no es solo una discográfica. Somos un colectivo de visionarios 
            que transformamos sonidos en experiencias, artistas en iconos y música 
            en movimientos culturales.
          </p>
          <p>
            Desde el underground hasta las principales plataformas, cultivamos 
            talento auténtico y llevamos el arte sonoro a nuevas dimensiones.
          </p>
          <div class="stats">
            <div class="stat">
              <span class="stat-number">50+</span>
              <span class="stat-label">ARTISTAS</span>
            </div>
            <div class="stat">
              <span class="stat-number">100M+</span>
              <span class="stat-label">STREAMS</span>
            </div>
            <div class="stat">
              <span class="stat-number">15</span>
              <span class="stat-label">PAÍSES</span>
            </div>
          </div>
        </div>
        <div class="about-visual">
          <div class="visual-element">
            <img src="@/assets/Sin Fondo_IMAGOTIPO.png" alt="METEORO Imagotipo" class="visual-imagotipo">
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

/* About Section */
.about-section {
  padding: 120px 0;
  background: var(--saturated-red);
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 80px;
  align-items: center;
}

.about-text {
  color: var(--white);
}

.about-text .section-title {
  color: var(--white);
  text-align: left;
  margin-bottom: 40px;
}

.about-text p {
  font-size: 1.3rem;
  line-height: 1.6;
  margin-bottom: 30px;
  opacity: 0.9;
  text-align: justify;
}

.stats {
  display: flex;
  gap: 60px;
  margin-top: 60px;
}

.stat {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stat-number {
  font-size: 3rem;
  font-weight: 900;
  color: var(--neon-yellow);
  line-height: 1;
}

.stat-label {
  font-size: 0.9rem;
  font-weight: 700;
  margin-top: 10px;
  letter-spacing: 1px;
}

.about-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.visual-element {
  width: 400px;
  height: 400px;
  background: var(--neon-yellow);
  border-radius: 50%;
  position: relative;
  animation: pulse 3s ease-in-out infinite;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.visual-imagotipo {
  width: 75%;
  height: auto;
  filter: contrast(1.2) brightness(0.1);
  transition: all 0.3s ease;
  animation: float-subtle 4s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(249, 255, 69, 0.4); }
  50% { transform: scale(1.05); box-shadow: 0 0 0 40px rgba(249, 255, 69, 0); }
}

@keyframes float-subtle {
  0%, 100% {
    transform: translateY(0) scale(1);
  }
  50% {
    transform: translateY(-10px) scale(1.05);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .stats {
    gap: 30px;
  }
}
</style> 