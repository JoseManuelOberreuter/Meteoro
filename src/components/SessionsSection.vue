<template>
  <section id="catalogo" class="sessions-section">
    <div class="section-container">
      <h2 class="section-title light">LANZAMIENTOS</h2>
      <div class="sessions-grid">
        <div
          v-for="session in sessions"
          :key="session.id"
          class="release-row"
          :class="{ wide: session.wide }"
        >
          <div
            class="release-cover"
            :class="{ wide: session.wide }"
            :style="{ backgroundImage: `url(${session.image})` }"
          ></div>
          <div class="release-info">
            <h3 class="release-title">{{ session.title }}</h3>
            <p class="release-artist">{{ session.artist }}</p>
            <p class="release-year">{{ session.date }}</p>
            <a
              class="play-button"
              :href="session.link || '#'"
              target="_blank"
              rel="noopener"
            >{{ session.buttonText || 'VER' }}</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { sessions } from '@/data/sessions.js'
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
  margin-bottom: 50px;
  letter-spacing: -1px;
  color: var(--black);
  border-bottom: 5px solid #000000;
  display: inline-block;
}

.section-title.light {
  color: #1A1A1A;
}

/* Sessions Section */
.sessions-section {
  padding: 120px 0 0 0;
  background: #F5F5F0;
}

.sessions-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 80px;
}

.release-row {
  display: grid;
  grid-template-columns: 380px 1fr;
  gap: 40px;
  align-items: center;
  height: 380px;
}

.release-row.wide {
  grid-template-columns: 760px 1fr;
}

.release-cover {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border: 4px solid #000000;
  background-color: #1A1A1A;
}

.release-cover.wide {
  height: 100%;
}

.release-info {
  display: flex;
  flex-direction: column;
  gap: 8px;
  height: 100%;
  justify-content: center;
}

.release-title {
  font-size: clamp(1.8rem, 4vw, 2.8rem);
  font-weight: 900;
  color: var(--black);
  margin: 0 0 6px 0;
}

.release-artist {
  color: #8F9499;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 1px;
  font-size: clamp(1rem, 2vw, 1.5rem);
  margin: 0;
}

.release-year {
  color: var(--black);
  opacity: 0.7;
  font-size: clamp(1rem, 2vw, 1.5rem);
  margin: 0 0 10px 0;
}

.play-button {
  width: fit-content;
  background: #000000;
  color: #FFFFFF;
  border: 2px solid #000000;
  padding: 12px 22px;
  font-weight: 900;
  letter-spacing: 0.5px;
  border-radius: 8px;
  cursor: pointer;
  display: inline-block;
  text-decoration: none;
  transition: transform 0.2s ease, background 0.2s ease, color 0.2s ease;
}

.play-button:hover {
  transform: translateY(-1px);
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .release-row {
    grid-template-columns: 1fr;
    gap: 20px;
    align-items: start;
    height: auto;
  }
  .release-cover {
    max-width: 380px;
    width: 100%;
    height: 320px;
  }
  .release-info {
    height: auto;
  }
}
</style> 