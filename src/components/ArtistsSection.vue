<template>
  <section id="artistas" class="artists-section">
    <div class="section-container">
      <h2 class="section-title">NUESTROS ARTISTAS</h2>
      <div class="artists-grid">
        <div 
          v-for="artist in artists" 
          :key="artist.id" 
          class="artist-card"
          @mouseenter="playHoverSound"
        >
          <div class="artist-image" :style="{ backgroundImage: `url(${artist.image})` }">
            <div class="artist-overlay">
              <h3>{{ artist.name }}</h3>
              <p>{{ artist.genre }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { artists } from '@/data/artists.js'

// Methods
const playHoverSound = () => {
  // Placeholder for hover sound effect
}
</script>

<style scoped>
/* Section Styles */
.section-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
}

.section-title {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Artists Section */
.artists-section {
  padding: 120px 0;
  background: #F5F5F0;
}

.artists-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 40px;
  max-width: 1400px;
  margin: 0 auto;
}

.artist-card {
  aspect-ratio: 2/3;
  position: relative;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.4s ease;
  border-radius: 4px;
  height: 600px;
}

.artist-card:hover {
  transform: scale(1.05);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
}

.artist-image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  position: relative;
}

.artist-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(26, 26, 26, 0.7);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: var(--white);
  opacity: 0;
  transition: all 0.3s ease;
  padding: 20px;
}

.artist-card:hover .artist-overlay {
  opacity: 1;
  background: rgba(26, 26, 26, 0.85);
}

.artist-overlay h3 {
  font-size: 1.8rem;
  font-weight: 900;
  margin-bottom: 10px;
  color: var(--neon-yellow);
  text-align: center;
  transform: translateY(20px);
  transition: transform 0.3s ease;
}

.artist-overlay p {
  font-size: 1rem;
  opacity: 0.8;
  text-align: center;
  transform: translateY(20px);
  transition: transform 0.3s ease 0.1s;
}

.artist-card:hover .artist-overlay h3,
.artist-card:hover .artist-overlay p {
  transform: translateY(0);
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .artists-grid {
    grid-template-columns: 1fr;
  }

  .artist-card {
    height: 500px;
  }
}
</style> 