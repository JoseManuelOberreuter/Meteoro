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
          <div class="artist-image" :style="{ backgroundImage: `url(${artist.image})` }">
            <div class="artist-overlay">
              <h3 :title="artist.name">{{ artist.name }}</h3>
              <p>{{ artist.genre }}</p>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Featured Artist Section -->
      <div id="featured-artist" class="featured-artist-section">
        <div class="featured-artist-container">
          <div class="featured-artist-image">
            <img :src="AlonsxTercerxImage" alt="ALONSX TERCERX" />
          </div>
          <div class="featured-artist-content text-right">
            <h2 class="featured-artist-title">ALONSX TERCERX</h2>
            <p class="featured-artist-description">
              ALONSX TERCERX es un proyecto artístico que cruza música 
              y performance, explorando sonoridades provenientes del funk, 
              el soul, la música disco y el R&B, pero siempre con rumbo 
              al pop de pista de baile.
            </p>
            <p class="featured-artist-description">
              Todo esto se articula con una identidad visual potente 
              y disidente, reflejada en el videoclip de "FUERTE", 
              primer single de su EP debut "TRES" (2025).
            </p>
            <div class="social-links">
              <a href="#" class="social-link">MUSICA</a>
              <a href="#" class="social-link">INSTAGRAM</a>
              <a href="#" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Neon Rebels Featured Section -->
      <div id="featured-neon-rebels" class="featured-artist-section">
        <div class="featured-artist-container reverse">
          <div class="featured-artist-image">
            <img :src="AlonsxTercerxImage" alt="DONATO SOTO" />
          </div>
          <div class="featured-artist-content">
            <h2 class="featured-artist-title">DONATO SOTO</h2>
            <p class="featured-artist-description">
              DONATO SOTO es el alter ego de Benjamín Cárdenas, alias 
              que utiliza desde 2017 para desarrollar una propuesta 
              de pop lo-fi marcada por una lírica que oscila entre 
              la sinceridad emocional y la ironía.
            </p>
            <p class="featured-artist-description">
              A la fecha ha publicado el EP "Carrete en el infierno" 
              (2018) y el álbum "Sapito de oro puro" (2020); y 
              actualmente se encuentra trabajando en su próxima 
              producción.
            </p>
            <div class="social-links">
              <a href="#" class="social-link">MUSICA</a>
              <a href="#" class="social-link">INSTAGRAM</a>
              <a href="#" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Aurora Beats Featured Section -->
      <div id="featured-aurora-beats" class="featured-artist-section">
        <div class="featured-artist-container">
          <div class="featured-artist-image">
            <img :src="AlonsxTercerxImage" alt="JOSEIKNACIO" />
          </div>
          <div class="featured-artist-content text-right">
            <h2 class="featured-artist-title">JOSEIKNACIO</h2>
            <p class="featured-artist-description">
              JOSEIKNACIO es un proyecto que nace desde la estética 
              indie pop con premisas lo-fi, para adentrarse en sonidos 
              de alta delicadeza y melancolía lírica, pero al mismo 
              tiempo envolventes y cálidos; elementos que se plasman 
              en su EP debut "Floración" (2019).
            </p>
            <p class="featured-artist-description">
              Tras una pausa, el proyecto retoma su camino con nuevo 
              material en desarrollo, el cual formará parte de distintos 
              lanzamientos previstos para los próximos meses.
            </p>
            <div class="social-links">
              <a href="#" class="social-link">MUSICA</a>
              <a href="#" class="social-link">INSTAGRAM</a>
              <a href="#" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
      
    </div>
  </section>
</template>

<script setup>
import { artists } from '@/data/artists.js'
import AlonsxTercerxImage from '@/assets/Alonsx_Tercerx_FOTO_V1.jpg'

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
    case 'JOSEIKNACIO':
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
  padding-top: 120px;
  padding-bottom: 0;
  background: #F5F5F0;
  margin-top: 40px;
}

.artists-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
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

.artist-card:hover {
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  transform: translateY(-5px);
  border-color: #FF6B6B;
}

.artist-image {
  width: 100%;
  height: 100%;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.artist-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
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
  background: rgba(0, 0, 0, 0.85);
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

/* Artist-Specific Styling */
.artist-card:hover .artist-overlay h3[title="ALONSX TERCERX"] {
  color: #FFD700;
  text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
}

.artist-card:hover .artist-overlay h3[title="DONATO SOTO"] {
  color: #00FFFF;
  text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
}

.artist-card:hover .artist-overlay h3[title="JOSEIKNACIO"] {
  color: #FF69B4;
  text-shadow: 0 0 10px rgba(255, 105, 180, 0.5);
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
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.8);
}

.artist-card:hover .click-indicator {
  transform: translateY(0);
}

@keyframes pulse {
  0%, 100% { opacity: 0.7; }
  50% { opacity: 1; }
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
    aspect-ratio: 0.8;
  }
  
  .featured-artist-section {
    margin-top: 60px;
    padding: 30px 0;
  }
  
  .featured-artist-container {
    flex-direction: column;
    gap: 30px;
  }

  .featured-artist-container.reverse {
    flex-direction: column;
  }

  .featured-artist-image {
    flex: 0 0 100%;
    max-width: 280px;
    margin: 0 auto;
    aspect-ratio: 0.8;
    background: #000000;
  }

  .featured-artist-content {
    padding-top: 0;
    text-align: left;
  }

  .featured-artist-content.text-right {
    text-align: center;
  }

  .featured-artist-title {
    font-size: 2rem;
    text-align: center;
    margin-bottom: 25px;
  }

  .featured-artist-description {
    font-size: 1rem;
    text-align: center;
  }
  
  .click-indicator {
    font-size: 0.8rem;
  }
  
  .social-links {
    justify-content: center;
    gap: 10px;
    margin-top: 20px;
  }
  
  .featured-artist-content.text-right .social-links {
    justify-content: center;
  }
  
  .social-link {
    font-size: 1.1rem;
  }
}

/* Featured Artist Section */
.featured-artist-section {
  margin-top: 80px;
  padding: 40px 0;
  border-bottom: 1px solid #e0e0e0;
}

.featured-artist-section:last-of-type {
  border-bottom: none;
}

.featured-artist-container {
  display: flex;
  gap: 60px;
  align-items: flex-start;
  max-width: 1200px;
  margin: 0 auto;
}

.featured-artist-container.reverse {
  flex-direction: row-reverse;
}

.featured-artist-image {
  flex: 0 0 350px;
  aspect-ratio: 0.8;
  overflow: hidden;
  border: 4px solid #000000;
  background: #000000;
}

.featured-artist-image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}

.featured-artist-content {
  flex: 1;
  text-align: left;
  padding-top: 20px;
}

.featured-artist-content.text-right {
  text-align: right;
}

.featured-artist-content.text-right .featured-artist-description {
  text-align: right;
}

.featured-artist-title {
  font-size: 3rem;
  font-weight: 900;
  color: #000000;
  margin-bottom: 30px;
  letter-spacing: -1px;
  border-bottom: 4px solid #000000;
  padding-bottom: 15px;
  display: inline-block;
}

.featured-artist-description {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #333333;
  margin-bottom: 20px;
  text-align: justify;
}

.social-links {
  display: flex;
  gap: 15px;
  margin-top: 30px;
}

.featured-artist-content.text-right .social-links {
  justify-content: flex-end;
}

.social-link {
  color: #000000;
  font-size: 1.3rem;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  display: inline-block;
  border-bottom: 2px solid transparent;
}

.social-link:hover {
  color: #ff0000;
  border-bottom: 2px solid #ff0000;
}

</style> 