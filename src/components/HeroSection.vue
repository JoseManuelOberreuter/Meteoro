<template>
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
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Props
defineProps({
  scrollTo: {
    type: Function,
    required: true
  }
})

// Reactive data
const heroText = ref(null)

// Lifecycle
onMounted(() => {
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
</script>

<style scoped>
/* Hero Section */
.hero {
  height: 100vh;
  background: #F5F5F0;
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
  color: #1A1A1A;
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.8s ease;
  line-height: 1.2;
  margin-bottom: 10px;
}

.title-line.highlight {
  color: var(--electric-blue);
  text-shadow: 0 0 30px rgba(51, 102, 204, 0.2);
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
  border-radius: 4px;
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
  mix-blend-mode: multiply;
}

.bg-shape {
  position: absolute;
  opacity: 0.08;
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
  background: var(--saturated-red);
}

.shape-3 {
  width: 200px;
  height: 600px;
  top: 20%;
  left: 5%;
  border-radius: 100px;
  animation-delay: 4s;
  background: var(--electric-blue);
}

.shape-4 {
  width: 400px;
  height: 400px;
  bottom: 10%;
  right: 15%;
  border-radius: 30px;
  transform: rotate(-15deg);
  animation-delay: 1s;
  background: #1A1A1A;
  opacity: 0.03;
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

/* Responsive Design */
@media (max-width: 480px) {
  .title-line {
    font-size: 2.5rem;
  }
  
  .cta-button {
    padding: 15px 30px;
    font-size: 1rem;
  }
}
</style> 