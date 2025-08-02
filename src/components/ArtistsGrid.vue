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
          @click="handleArtistClick(artist)"
        >
          <div class="artist-image">
            <img :src="artist.image" :alt="artist.name" />
            <div class="artist-overlay">
              <h3 :title="artist.name">{{ artist.name }}</h3>
              <p>{{ artist.genre }}</p>
              <div class="click-indicator">TAP PARA VER MÁS</div>
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

const handleArtistClick = (artist) => {
  let targetSectionId = '';
  
  // Determinar la sección objetivo basada en el nombre del artista
  switch (artist.name) {
    case 'ALONSX TERCERX':
      targetSectionId = 'featured-artist';
      break;
    case 'DONATO SOTO':
      targetSectionId = 'featured-neon-rebels';
      break;
    case 'JOSEI KNACIO':
      targetSectionId = 'featured-aurora-beats';
      break;
    default:
      return; // Si no coincide con ningún artista, no hacer nada
  }
  
  // Hacer scroll a la sección correspondiente
  const featuredSection = document.getElementById(targetSectionId);
  if (featuredSection) {
    featuredSection.scrollIntoView({ 
      behavior: 'smooth',
      block: 'start'
    });
  }
}
</script>

<style scoped>
/* Section Styles */
.section-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
}

/* Reset para cards */
.artist-card * {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
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
  margin-top: 60px;
  padding: 120px 0;
  background: #F5F5F0;
}

.artists-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 1400px;
  margin: 0px auto;
  justify-content: space-between;
  align-items: center;
}

.artist-card {
  width: 100%;
  max-width: 350px;
  aspect-ratio: 0.8;
  position: relative;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.4s ease;
  border: 4px solid #000000;
  display: flex;
  flex-direction: column;
  padding: 0;
  margin: 0;
  background: #000000;
}

/* Posicionamiento específico de cada tarjeta */
.artist-card:nth-child(1) {
  justify-self: start;
}

.artist-card:nth-child(2) {
  justify-self: center;
}

.artist-card:nth-child(3) {
  justify-self: end;
}

.artist-card:hover {
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  transform: translateY(-5px);
  border-color: #ff0000;
}

.artist-image {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
}

.artist-image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
  display: block;
}

.artist-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.6);
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
  background: rgba(0, 0, 0, 0.7);
}

.artist-overlay h3 {
  font-size: 1.8rem;
  font-weight: 900;
  margin-bottom: 10px;
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

/* Artist-Specific Styling */
.artist-card:hover .artist-overlay h3[title="ALONSX TERCERX"] {
  color: #ffffff;
}

.artist-card:hover .artist-overlay h3[title="DONATO SOTO"] {
  color: #ffffff;
}

.artist-card:hover .artist-overlay h3[title="JOSEIKNACIO"] {
  color: #ffffff;
}

.click-indicator {
  font-size: 0.9rem;
  color: #ffffff;
  font-weight: 600;
  margin-top: 15px;
  animation: pulse 2s infinite;
  text-align: center;
  transform: translateY(20px);
  transition: transform 0.3s ease 0.2s;
}

.artist-card:hover .click-indicator {
  transform: translateY(0);
}

@keyframes pulse {
  0%, 100% { opacity: 0.7; }
  50% { opacity: 1; }
}

/* Responsive Design */

/* Large tablets and small desktops */
@media (max-width: 1024px) {
  .artists-section {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  .section-container {
    padding: 0 30px;
  }
  
  .artists-grid {
    gap: 25px;
    max-width: 100%;
    align-items: center;
  }
  
  .artist-card {
    max-width: 320px;
  }
}

/* Tablets */
@media (max-width: 768px) {
  .artists-section {
    padding-top: 100px;
    padding-bottom: 30px;
    margin-top: 20px;
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  .section-container {
    padding: 0 20px;
  }
  
  .artists-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    max-width: 100%;
    justify-items: center;
    align-items: center;
  }

  .artist-card {
    max-width: 280px;
    aspect-ratio: 0.85;
    margin: 0;
    border: 3px solid #000000;
    background: #000000;
  }
  
  .artist-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
  }
  
  .artist-overlay {
    padding: 15px;
  }
  
  .artist-overlay h3 {
    font-size: 1.4rem;
    margin-bottom: 8px;
  }
  
  .artist-overlay p {
    font-size: 0.9rem;
  }
}

/* Mobile devices */
@media (max-width: 600px) {
  .artists-section {
    padding-top: 90px;
    padding-bottom: 25px;
    margin-top: 15px;
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  .section-container {
    padding: 0 15px;
  }
  
  .artists-grid {
    grid-template-columns: 1fr;
    gap: 25px;
    max-width: 100%;
    justify-items: center;
    align-items: center;
  }

  .artist-card {
    max-width: 100%;
    aspect-ratio: 0.8;
    margin: 0 auto;
    border: 3px solid #000000;
    background: #000000;
  }
  
  .artist-overlay h3 {
    font-size: 1.5rem;
    margin-bottom: 8px;
  }
  
  .artist-overlay p {
    font-size: 0.9rem;
  }
  
  .click-indicator {
    font-size: 0.8rem;
    margin-top: 10px;
  }
}

/* Small mobile devices */
@media (max-width: 480px) {
  .artists-section {
    padding-top: 80px;
    padding-bottom: 20px;
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  .section-container {
    padding: 0 12px;
  }
  
  .artists-grid {
    gap: 20px;
  }
  
  .artist-card {
    aspect-ratio: 0.75;
    border: 3px solid #000000;
    background: #000000;
    min-height: 260px;
  }
  
  .artist-overlay {
    padding: 12px;
  }
  
  .artist-overlay h3 {
    font-size: 1.2rem;
    margin-bottom: 6px;
  }
  
  .artist-overlay p {
    font-size: 0.85rem;
  }
  
  .click-indicator {
    font-size: 0.75rem;
    margin-top: 8px;
  }
}

/* Touch device optimizations */
@media (hover: none) and (pointer: coarse) {
  .artist-card:hover {
    transform: none;
    box-shadow: none;
    border-color: #000000;
  }
  
  .artist-overlay {
    opacity: 0.8;
    background: rgba(0, 0, 0, 0.6);
  }
  
  .artist-overlay h3,
  .artist-overlay p,
  .click-indicator {
    transform: translateY(0);
  }
  
  .click-indicator {
    opacity: 1;
    animation: pulse 2s infinite;
    background: rgba(255, 255, 255, 0.1);
    padding: 8px 12px;
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    font-size: 0.8rem;
    font-weight: 600;
  }
  
  .artist-card:active {
    transform: scale(0.98);
  }
}

/* Additional mobile-specific improvements */
@media (max-width: 768px) {
  .artists-section {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  .artist-card {
    /* Improve tap target size */
    min-height: 280px;
    background: #000000;
    transition: all 0.3s ease;
  }
  
  .artist-card:active {
    transform: scale(0.98);
  }
  
  .artist-overlay {
    /* Always show overlay on mobile for better UX */
    opacity: 0.7;
    background: rgba(0, 0, 0, 0.5);
  }
  
  .artist-overlay h3,
  .artist-overlay p,
  .click-indicator {
    transform: translateY(0);
  }
  
  .click-indicator {
    opacity: 1;
    background: rgba(255, 255, 255, 0.15);
    padding: 6px 10px;
    border-radius: 15px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    font-size: 0.75rem;
    font-weight: 600;
    margin-top: 10px;
    transition: all 0.2s ease;
  }
}
</style> 