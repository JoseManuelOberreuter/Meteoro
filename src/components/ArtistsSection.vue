<template>
  <section id="artistas" class="artists-section">
    <div class="section-container">
      
      <!-- Featured Artist Section -->
      <div id="featured-artist" class="featured-artist-section">
        <div class="featured-artist-container">
          <div class="featured-artist-image">
            <video :src="AlonsxTercerxVideo" autoplay loop muted playsinline></video>
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
              <a href="https://offstep.link/782180063251" target="_blank" class="social-link">MUSICA</a>
              <a href="https://www.instagram.com/alonsxtercerx?igsh=MXVrazQyc2pqbnRkNg%3D%3D" target="_blank" class="social-link">INSTAGRAM</a>
              <a href="https://www.youtube.com/@alonsxtercerx" target="_blank" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Neon Rebels Featured Section -->
      <div id="featured-neon-rebels" class="featured-artist-section">
        <div class="featured-artist-container reverse">
          <div class="featured-artist-image">
            <video :src="DonatoSotoVideo" autoplay loop muted playsinline></video>
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
              <a href="#" target="_blank" class="social-link">MUSICA</a>
              <a href="https://www.instagram.com/donato_soto?igsh=MXU3bXF4aGRibjQycg==" target="_blank" class="social-link">INSTAGRAM</a>
              <a href="#" target="_blank" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Aurora Beats Featured Section -->
      <div id="featured-aurora-beats" class="featured-artist-section">
        <div class="featured-artist-container">
          <div class="featured-artist-image">
            <video :src="JoseiKacioVideo" autoplay loop muted playsinline></video>
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
              <a href="#" target="_blank" class="social-link">MUSICA</a>
              <a href="https://www.instagram.com/joseiknacio?igsh=MWt4aHViOTk4NGRldA==" target="_blank" class="social-link">INSTAGRAM</a>
              <a href="#" target="_blank" class="social-link">YOUTUBE</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { artists } from '@/data/artists.js'
import AlonsxTercerxVideo from '@/assets/ALONSXTERCERX_CLIP_WEB.mp4'
import DonatoSotoVideo from '@/assets/DONATO_SOTO_CLIP_WEB.mp4'
import JoseiKacioVideo from '@/assets/JOSEIKNACIO_CLIP_WEB.mp4'

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
  min-height: 100vh;
  display: flex;
  align-items: center;
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
  color: #ffffff;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
}

.artist-card:hover .artist-overlay h3[title="DONATO SOTO"] {
  color: #ffffff;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
}

.artist-card:hover .artist-overlay h3[title="JOSEIKNACIO"] {
  color: #ffffff;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
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
  
  /* Featured Artist Sections - Mobile */
  .featured-artist-section {
    margin-top: 40px;
    padding: 60px 0;
    border-bottom: 1px solid #e0e0e0;
    min-height: 100vh;
    display: flex;
    align-items: center;
  }

  /* First featured section needs extra padding to account for fixed navbar on mobile */
  .featured-artist-section:first-of-type {
    padding-top: 120px;
  }
  
  .featured-artist-container {
    flex-direction: column;
    gap: 0;
    align-items: center;
    width: 100%;
  }

  .featured-artist-container.reverse {
    flex-direction: column;
  }

  .featured-artist-image {
    display: none;
  }

  .featured-artist-content {
    padding-top: 0;
    text-align: center;
    width: 100%;
    max-width: 100%;
    padding: 0 20px;
  }

  .featured-artist-content.text-right {
    text-align: center;
  }

  .featured-artist-title {
    font-size: 2.2rem;
    text-align: center !important;
    margin-top: 0;
    margin-bottom: 25px;
    padding-bottom: 15px;
    border-bottom: 3px solid #000000;
    font-weight: 900;
    width: 100%;
  }

  .featured-artist-description {
    font-size: 1.1rem;
    text-align: justify !important;
    margin-bottom: 20px;
    line-height: 1.6;
    color: #333333;
    width: 100%;
    max-width: 100%;
  }
  
  .featured-artist-content.text-right .featured-artist-description {
    text-align: justify !important;
  }
  
  .featured-artist-content.text-right .featured-artist-title {
    text-align: center !important;
  }
  
  .social-links {
    justify-content: center !important;
    gap: 15px;
    margin-top: 25px;
    flex-wrap: wrap;
    width: 100%;
  }
  
  .featured-artist-content.text-right .social-links {
    justify-content: center !important;
  }
  
  .social-link {
    font-size: 1.1rem;
    padding: 5px 10px;
    border-radius: 4px;
    transition: all 0.3s ease;
  }
  
  .social-link:hover {
    background: #ff0000;
    color: #ffffff;
    border-bottom: 2px solid #ff0000;
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
  
  /* Featured sections - smaller mobile */
  .featured-artist-section {
    margin-top: 30px;
    padding: 40px 0;
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  
  /* First featured section needs extra padding to account for fixed navbar on smaller mobile */
  .featured-artist-section:first-of-type {
    padding-top: 100px;
  }
  
  .featured-artist-container {
    gap: 0;
    width: 100%;
  }
  
  .featured-artist-image {
    display: none;
  }
  
  .featured-artist-content {
    padding: 0 15px;
    text-align: center;
    width: 100%;
  }
  
  .featured-artist-content.text-right {
    text-align: center;
  }
  
  .featured-artist-title {
    font-size: 1.9rem;
    margin-top: 0;
    margin-bottom: 20px;
    padding-bottom: 12px;
    border-bottom: 2px solid #000000;
    text-align: center !important;
    width: 100%;
  }
  
  .featured-artist-description {
    font-size: 1rem;
    margin-bottom: 18px;
    text-align: justify !important;
    line-height: 1.6;
    width: 100%;
    max-width: 100%;
  }
  
  .featured-artist-content.text-right .featured-artist-description {
    text-align: justify !important;
  }
  
  .featured-artist-content.text-right .featured-artist-title {
    text-align: center !important;
  }
  
  .social-links {
    gap: 10px;
    margin-top: 20px;
    justify-content: center !important;
    width: 100%;
  }
  
  .social-link {
    font-size: 1rem;
    padding: 4px 8px;
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
  
  .social-link:active {
    transform: scale(0.95);
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
  
  /* Hide all featured artist images on mobile */
  .featured-artist-image {
    display: none !important;
  }
  
  /* Ensure text content takes full width and proper alignment */
  .featured-artist-content {
    width: 100% !important;
    max-width: 100% !important;
    text-align: center !important;
    padding: 0 20px !important;
  }
  
  .featured-artist-content.text-right {
    text-align: center !important;
  }
  
  /* Force all descriptions to be justified on mobile */
  .featured-artist-description {
    text-align: justify !important;
    width: 100% !important;
    max-width: 100% !important;
  }
  
  .featured-artist-content.text-right .featured-artist-description {
    text-align: justify !important;
  }
  
  /* Force centering of titles and social links on mobile */
  .featured-artist-title {
    text-align: center !important;
    width: 100% !important;
  }
  
  .featured-artist-content.text-right .featured-artist-title {
    text-align: center !important;
  }
  
  .social-links {
    justify-content: center !important;
    width: 100% !important;
  }
  
  .featured-artist-content.text-right .social-links {
    justify-content: center !important;
  }
  
  /* Ensure containers take full width */
  .featured-artist-container {
    width: 100% !important;
  }
}

/* Featured Artist Section */
.featured-artist-section {
  margin-top: 80px;
  padding: 150px 0;
  border-bottom: 1px solid #e0e0e0;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

/* First featured section needs extra padding to account for fixed navbar */
.featured-artist-section:first-of-type {
  padding-top: 160px;
}

.featured-artist-section:last-of-type {
  border-bottom: none;
}

.featured-artist-container {
  display: flex;
  gap: 60px;
  align-items: flex-start;
  max-width: 1400px;
  margin: 0 auto;
}

.featured-artist-container.reverse {
  flex-direction: row-reverse;
}

.featured-artist-image {
  flex: 0 0 350px;
  overflow: hidden;
  border: 2px solid #000000;
  background: #000000;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 15px;
}

.featured-artist-image img,
.featured-artist-image video {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  object-position: center;
}

.featured-artist-content {
  flex: 1;
  text-align: left;
  padding-top: 0;
}

.featured-artist-content.text-right {
  text-align: right;
}

.featured-artist-content.text-right .featured-artist-description {
  text-align: right;
  margin-left: auto;
}

.featured-artist-title {
  font-size: 3rem;
  font-weight: 900;
  color: #000000;
  margin-top: 0;
  margin-bottom: 30px;
  letter-spacing: -1px;
  border-bottom: 4px solid #000000;
  display: inline-block;
}

.featured-artist-description {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #333333;
  margin-bottom: 20px;
  text-align: justify;
  max-width: 75%;
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