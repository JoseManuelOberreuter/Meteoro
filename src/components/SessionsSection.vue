<template>
  <section id="catalogo" class="sessions-section">
    <div class="section-container">
      <h2 class="section-title light">LANZAMIENTOS</h2>
      <div class="sessions-grid">
        <div 
          v-for="session in sessions" 
          :key="session.id" 
          class="session-card"
        >
          <div 
            class="session-video"
            :style="{ backgroundImage: `url(${session.image})` }"
          >
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
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 40px;
}

.session-card {
  background: var(--white);
  overflow: hidden;
  transition: all 0.4s ease;
  border: 4px solid #000000;
}

.session-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 30px 80px rgba(0, 0, 0, 0.2);
}

.session-video {
  aspect-ratio: 16/9;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  cursor: pointer;
  transition: all 0.3s ease;
  background-color: #1A1A1A;
}

.session-video:hover {
  transform: scale(1.02);
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
  background: rgba(0, 0, 0, 0.4);
  transition: all 0.3s ease;
}

.session-video:hover .video-overlay {
  background: rgba(0, 0, 0, 0.2);
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

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .sessions-grid {
    grid-template-columns: 1fr;
  }
}
</style> 