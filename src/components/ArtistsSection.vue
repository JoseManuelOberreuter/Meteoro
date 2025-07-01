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
            <img src="https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?q=80&w=1000&auto=format&fit=crop" alt="Luna Eclipse" />
          </div>
          <div class="featured-artist-content text-right">
            <h2 class="featured-artist-title">LUNA ECLIPSE</h2>
            <p class="featured-artist-description">
              LUNA ECLIPSE es un proyecto de electronic soul que 
              fusiona sonidos etéreos con ritmos profundos, 
              creando paisajes sonoros únicos y envolventes.
            </p>
            <p class="featured-artist-description">
                            Con una identidad artística que explora la conexión 
              entre lo cósmico y lo terrenal, Luna Eclipse presenta 
              composiciones que invitan a la introspección y el 
              movimiento, llevando al oyente a un viaje emocional 
              a través de texturas sonoras innovadoras.
            </p>
            <div class="social-links">
              <a href="#" class="social-link">YOUTUBE</a>
              <a href="#" class="social-link">INSTAGRAM</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Neon Rebels Featured Section -->
      <div id="featured-neon-rebels" class="featured-artist-section">
        <div class="featured-artist-container reverse">
          <div class="featured-artist-image">
            <img src="https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?q=80&w=1000&auto=format&fit=crop" alt="Neon Rebels" />
          </div>
          <div class="featured-artist-content">
            <h2 class="featured-artist-title">NEON REBELS</h2>
            <p class="featured-artist-description">
              NEON REBELS es una banda de indie rock que combina 
              guitarras distorsionadas con melodías pegajosas y 
              letras introspectivas que reflejan la experiencia 
              urbana contemporánea.
            </p>
            <p class="featured-artist-description">
              Con un sonido que fusiona el indie rock clásico con 
              elementos modernos, Neon Rebels crea atmósferas 
              nostálgicas y energéticas que conectan con una nueva 
              generación de oyentes buscando autenticidad y rebeldía 
              en la música.
            </p>
            <div class="social-links">
              <a href="#" class="social-link">YOUTUBE</a>
              <a href="#" class="social-link">INSTAGRAM</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Aurora Beats Featured Section -->
      <div id="featured-aurora-beats" class="featured-artist-section">
        <div class="featured-artist-container">
          <div class="featured-artist-image">
            <img src="https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=1000&auto=format&fit=crop" alt="Aurora Beats" />
          </div>
          <div class="featured-artist-content text-right">
            <h2 class="featured-artist-title">AURORA BEATS</h2>
            <p class="featured-artist-description">
              AURORA BEATS es un proyecto experimental que explora 
              las fronteras del sonido, fusionando elementos de 
              ambient, techno y música concreta para crear paisajes 
              sonoros únicos e inmersivos.
            </p>
            <p class="featured-artist-description">
              Cada composición de Aurora Beats es un viaje sonoro 
              que desafía las convenciones musicales tradicionales, 
              invitando al oyente a explorar nuevas dimensiones 
              auditivas a través de texturas, ritmos y atmosferas 
              completamente innovadoras.
            </p>
            <div class="social-links">
              <a href="#" class="social-link">YOUTUBE</a>
              <a href="#" class="social-link">INSTAGRAM</a>
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
    case 'LUNA ECLIPSE':
      targetSectionId = 'featured-artist';
      break;
    case 'NEON REBELS':
      targetSectionId = 'featured-neon-rebels';
      break;
    case 'AURORA BEATS':
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
  margin-top: 40px;
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
  border: 4px solid #000000;
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

/* Artist-Specific Styling */
.artist-card:hover .artist-overlay h3[title="LUNA ECLIPSE"] {
  color: #FFD700;
  text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
}

.artist-card:hover .artist-overlay h3[title="NEON REBELS"] {
  color: #00FFFF;
  text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
}

.artist-card:hover .artist-overlay h3[title="AURORA BEATS"] {
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
    height: 500px;
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
    max-width: 300px;
    margin: 0 auto;
    aspect-ratio: 1/1;
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
    padding: 8px 16px;
    font-size: 0.8rem;
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
  flex: 0 0 400px;
  aspect-ratio: 3/4;
  overflow: hidden;
  border-radius: 8px;
  border: 4px solid #000000;
}

.featured-artist-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
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
  background: #000000;
  color: #ffffff;
  padding: 10px 20px;
  font-size: 0.9rem;
  font-weight: 600;
  text-decoration: none;
  border-radius: 4px;
  transition: all 0.3s ease;
  display: inline-block;
}

.social-link:hover {
  background: #333333;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

</style> 