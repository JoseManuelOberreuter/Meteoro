<template>
  <div id="app">
    <!-- Navigation -->
    <nav class="nav" :class="{ 'nav-scrolled': isScrolled }">
      <div class="nav-container">
          <div class="nav-brand">
          <h1>METEORO</h1>
        </div>
        <div class="nav-menu">
          <a href="#artistas" @click="scrollTo('artistas')">ARTISTAS</a>
          <a href="#sesiones" @click="scrollTo('sesiones')">SESIONES</a>
          <a href="#sobre" @click="scrollTo('sobre')">SOBRE NOSOTROS</a>
          <a href="#contacto" @click="scrollTo('contacto')">CONTACTO</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <div class="hero-text" ref="heroText">
          <h1 class="hero-title">
            <span class="title-line">EL PUENTE ENTRE</span>
            <span class="title-line highlight">EL TALENTO EMERGENTE</span>
            <span class="title-line accent">Y EL ESCENARIO QUE MERECE</span>
          </h1>
          <button class="cta-button" @click="scrollTo('artistas')">
            DESCUBRE EL TALENTO
          </button>
        </div>
      </div>
      <div class="hero-bg-elements">
        <div class="bg-shape shape-1"></div>
        <div class="bg-shape shape-2"></div>
        <div class="bg-shape shape-3"></div>
        <div class="bg-shape shape-4"></div>
        </div>
      </section>

    <!-- Artists Section -->
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

    <!-- Marquee Section -->
    <section class="marquee-section">
      <div class="marquee-container">
        <div class="marquee-track">
          <div class="marquee-item">LOREM IPSUM DOLOR SIT AMET • CONSECTETUR ADIPISCING • ELIT SED DO EIUSMOD</div>
        </div>
      </div>
    </section>

    <!-- Sessions Section -->
    <section id="sesiones" class="sessions-section">
      <div class="section-container">
        <h2 class="section-title light">SESIONES EN VIVO</h2>
        <div class="sessions-grid">
          <div 
            v-for="session in sessions" 
            :key="session.id" 
            class="session-card"
          >
            <div class="session-video">
              <div class="video-overlay">
                <div class="play-icon">▶</div>
              </div>
            </div>
            <div class="session-info">
              <h3>{{ session.title }}</h3>
              <p>{{ session.artist }} • {{ session.date }}</p>
            </div>
            </div>
          </div>
        </div>
      </section>

    <!-- About Section -->
    <section id="sobre" class="about-section">
      <div class="section-container">
        <div class="about-content">
          <div class="about-text">
            <h2 class="section-title">SOBRE NOSOTROS</h2>
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
            <div class="visual-element"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Green Marquee Section -->
    <section class="marquee-section green-marquee">
      <div class="marquee-container">
        <div class="marquee-track">
          <div class="marquee-item">DESCUBRE • INNOVA • TRANSFORMA • IMPACTA • EVOLUCIONA</div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
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

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2024 METEORO. MÁS QUE MÚSICA, SOMOS IMPACTO.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Reactive data
const isScrolled = ref(false)
const heroText = ref(null)

// Mock data
const artists = [
  { 
    id: 1, 
    name: 'LUNA ECLIPSE', 
    genre: 'ELECTRONIC SOUL',
    image: 'https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?q=80&w=1000&auto=format&fit=crop'
  },
  { 
    id: 2, 
    name: 'NEON REBELS', 
    genre: 'INDIE ROCK',
    image: 'https://images.unsplash.com/photo-1493225457124-a3eb161ffa5f?q=80&w=1000&auto=format&fit=crop'
  },
  { 
    id: 3, 
    name: 'AURORA BEATS', 
    genre: 'EXPERIMENTAL',
    image: 'https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=1000&auto=format&fit=crop'
  },
  { 
    id: 4, 
    name: 'CYBER FOLK', 
    genre: 'FOLK FUSION',
    image: 'https://images.unsplash.com/photo-1514320291840-2e0a9bf2a9ae?q=80&w=1000&auto=format&fit=crop'
  },
  { 
    id: 5, 
    name: 'DARK MATTER', 
    genre: 'AMBIENT TECHNO',
    image: 'https://images.unsplash.com/photo-1470225620780-dba8ba36b745?q=80&w=1000&auto=format&fit=crop'
  },
  { 
    id: 6, 
    name: 'STELLAR VOID', 
    genre: 'SHOEGAZE',
    image: 'https://images.unsplash.com/photo-1501612780327-45045538702b?q=80&w=1000&auto=format&fit=crop'
  }
]

const sessions = [
  { 
    id: 1, 
    title: 'LIVE SESSION #01', 
    artist: 'LUNA ECLIPSE', 
    date: '2024',
    image: 'https://images.unsplash.com/photo-1470229722913-7c0e2dbbafd3?q=80&w=2070'
  },
  { 
    id: 2, 
    title: 'ACOUSTIC SERIES', 
    artist: 'CYBER FOLK', 
    date: '2024',
    image: 'https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?q=80&w=2070'
  },
  { 
    id: 3, 
    title: 'UNDERGROUND VIBES', 
    artist: 'DARK MATTER', 
    date: '2024',
    image: 'https://images.unsplash.com/photo-1574169208507-84376144848b?q=80&w=2079'
  }
]

// Methods
const scrollTo = (elementId) => {
  const element = document.getElementById(elementId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const playHoverSound = () => {
  // Placeholder for hover sound effect
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

// Lifecycle
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  
  // Animate hero text on load
  if (heroText.value) {
    const lines = heroText.value.querySelectorAll('.title-line')
    lines.forEach((line, index) => {
      setTimeout(() => {
        line.style.opacity = '1'
        line.style.transform = 'translateY(0)'
      }, index * 200)
    })
  }
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style>
/* Reset and base styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Arial Black', 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.4;
  color: #1A1A1A;
  background-color: #F3F0EA;
  overflow-x: hidden;
}

/* Color variables */
:root {
  --black: #1A1A1A;
  --white: #F3F0EA;
  --neon-yellow: #F9FF45;
  --electric-blue: #3366CC;
  --saturated-red: #F73939;
}

/* Navigation */
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 20px 0;
  background: transparent;
  transition: all 0.3s ease;
}

.nav-scrolled {
  background: rgba(26, 26, 26, 0.95);
  backdrop-filter: blur(10px);
  padding: 15px 0;
}

.nav-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand h1 {
  font-size: 2rem;
  font-weight: 900;
  color: var(--neon-yellow);
  letter-spacing: 2px;
}

.nav-menu {
  display: flex;
  gap: 40px;
}

.nav-menu a {
  color: var(--white);
  text-decoration: none;
  font-weight: 700;
  font-size: 0.9rem;
  letter-spacing: 1px;
  transition: all 0.3s ease;
  position: relative;
}

.nav-menu a:hover {
  color: var(--neon-yellow);
  transform: translateY(-2px);
}

.nav-menu a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--neon-yellow);
  transition: width 0.3s ease;
}

.nav-menu a:hover::after {
  width: 100%;
}

/* Hero Section */
.hero {
  height: 100vh;
  background: linear-gradient(135deg, #000000 0%, #0A0A0A 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero-content {
  text-align: center;
  z-index: 2;
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero-title {
  display: flex;
  flex-direction: column;
  gap: 5px;
  margin-bottom: 40px;
  padding: 0 20px;
}

.title-line {
  font-size: clamp(2rem, 5vw, 5rem);
  font-weight: 900;
  letter-spacing: -1px;
  color: var(--white);
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.8s ease;
  line-height: 1.2;
  margin-bottom: 10px;
}

.title-line.highlight {
  color: var(--neon-yellow);
  text-shadow: 0 0 30px rgba(249, 255, 69, 0.5);
}

.title-line.accent {
  color: var(--saturated-red);
  font-style: italic;
}

.cta-button {
  background: var(--electric-blue);
  color: var(--white);
  border: none;
  padding: 20px 50px;
  font-size: 1.2rem;
  font-weight: 900;
  letter-spacing: 2px;
  cursor: pointer;
  transition: all 0.3s ease;
  border-radius: 0;
  position: relative;
  overflow: hidden;
}

.cta-button:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(51, 102, 204, 0.3);
}

.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.5s ease;
}

.cta-button:hover::before {
  left: 100%;
}

/* Background Elements */
.hero-bg-elements {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  mix-blend-mode: screen;
}

.bg-shape {
  position: absolute;
  opacity: 0.15;
  animation: float 6s ease-in-out infinite;
  filter: blur(5px);
}

.shape-1 {
  width: 500px;
  height: 500px;
  top: 5%;
  right: 5%;
  border-radius: 50%;
  animation-delay: 0s;
  background: var(--electric-blue);
}

.shape-2 {
  width: 300px;
  height: 300px;
  bottom: 15%;
  left: 10%;
  transform: rotate(45deg);
  animation-delay: 2s;
  background: var(--neon-yellow);
}

.shape-3 {
  width: 200px;
  height: 600px;
  top: 20%;
  left: 5%;
  border-radius: 100px;
  animation-delay: 4s;
  background: var(--saturated-red);
}

.shape-4 {
  width: 400px;
  height: 400px;
  bottom: 10%;
  right: 15%;
  border-radius: 30px;
  transform: rotate(-15deg);
  animation-delay: 1s;
  background: var(--white);
  opacity: 0.05;
}

@keyframes float {
  0%, 100% { 
    transform: translateY(0px) rotate(0deg); 
    opacity: 0.15;
  }
  50% { 
    transform: translateY(-20px) rotate(10deg);
    opacity: 0.2;
  }
}

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

.section-title.light {
  color: var(--white);
}

/* Artists Section */
.artists-section {
  padding: 120px 0;
  background: var(--white);
}

.artists-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 40px;
}

.artist-card {
  aspect-ratio: 1;
  position: relative;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.4s ease;
  border-radius: 4px;
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

/* Sessions Section */
.sessions-section {
  padding: 120px 0;
  background: var(--black);
}

.sessions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 40px;
}

.session-card {
  background: var(--white);
  overflow: hidden;
  transition: all 0.4s ease;
}

.session-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 30px 80px rgba(249, 255, 69, 0.2);
}

.session-video {
  aspect-ratio: 16/9;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.session-video:hover {
  transform: scale(1.05);
}

.video-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.3);
  transition: background 0.3s ease;
}

.session-video:hover .video-overlay {
  background: rgba(0, 0, 0, 0.1);
}

.play-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--neon-yellow);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  color: var(--black);
  transition: all 0.3s ease;
}

.session-video:hover .play-icon {
  transform: scale(1.1);
}

.session-info {
  padding: 30px;
}

.session-info h3 {
  font-size: 1.5rem;
  font-weight: 900;
  margin-bottom: 10px;
  color: var(--black);
}

.session-info p {
  color: var(--black);
  opacity: 0.7;
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
  width: 300px;
  height: 300px;
  background: var(--neon-yellow);
  border-radius: 50%;
  position: relative;
  animation: pulse 3s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(249, 255, 69, 0.4); }
  50% { transform: scale(1.05); box-shadow: 0 0 0 40px rgba(249, 255, 69, 0); }
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

/* Footer */
.footer {
  background: var(--black);
  padding: 40px 0;
}

.footer-content {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
  text-align: center;
}

.footer-content p {
  color: var(--white);
  font-weight: 700;
  opacity: 0.8;
}

/* Responsive Design */
@media (max-width: 768px) {
  .nav-container {
    padding: 0 20px;
    flex-direction: column;
    gap: 20px;
  }
  
  .nav-menu {
    gap: 20px;
  }
  
  .section-container {
    padding: 0 20px;
  }
  
  .artists-grid {
    grid-template-columns: 1fr;
  }
  
  .sessions-grid {
    grid-template-columns: 1fr;
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .stats {
    gap: 30px;
  }
  
  .social-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .nav-brand h1 {
    font-size: 1.5rem;
  }
  
  .nav-menu {
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .title-line {
    font-size: 2.5rem;
  }
  
  .cta-button {
    padding: 15px 30px;
    font-size: 1rem;
  }
  
  .artists-grid {
    grid-template-columns: 1fr;
  }
  
  .sessions-grid {
    grid-template-columns: 1fr;
  }
}

/* Marquee Section */
.marquee-section {
  height: 120px;
  overflow: hidden;
  position: relative;
  display: flex;
  align-items: center;
}

/* Red Marquee */
.marquee-section:not(.green-marquee) {
  background: linear-gradient(90deg, var(--saturated-red) 0%, #ff1f1f 50%, var(--saturated-red) 100%);
}

/* Green Marquee */
.green-marquee {
  background: linear-gradient(90deg, #2ECC71 0%, #27AE60 50%, #2ECC71 100%);
}

.marquee-container {
  width: 100%;
  overflow: hidden;
  position: relative;
}

.marquee-track {
  display: flex;
  gap: 2rem;
}

.marquee-item {
  font-size: 4rem;
  font-weight: 900;
  text-transform: uppercase;
  padding: 0 2rem;
  text-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  opacity: 0.9;
  white-space: nowrap;
  animation: slideIn 10s linear infinite;
  transform: translateX(100vw);
}

.marquee-section:not(.green-marquee) .marquee-item {
  color: var(--white);
}

.green-marquee .marquee-item {
  color: var(--black);
  text-shadow: 0 2px 5px rgba(255, 255, 255, 0.2);
}

.marquee-item:nth-child(2) {
  animation-delay: 1s;
}

.marquee-item:nth-child(3) {
  animation-delay: 2s;
}

.marquee-item:nth-child(4) {
  animation-delay: 3s;
}

.marquee-item:nth-child(5) {
  animation-delay: 4s;
}

@keyframes slideIn {
  0% {
    transform: translateX(100vw);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>