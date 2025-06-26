<template>
  <nav class="nav" :class="{ 'nav-scrolled': isScrolled }">
    <div class="nav-container">
      <div class="nav-brand">
        <a href="#" @click.prevent="scrollTo('app')" class="nav-brand-link">
          <img src="@/assets/LOGO HEADER METEORO.png" alt="METEORO Logo" class="nav-logo">
        </a>
      </div>
      <div class="nav-menu">
        <a href="#catalogo" @click="scrollTo('catalogo')">CATÁLOGO</a>
        <a href="#sobre" @click="scrollTo('sobre')">SOBRE NOSOTRXS</a>
        <a href="#noticias" @click="scrollTo('noticias')">NOTICIAS</a>
        <a href="#tienda" @click="scrollTo('tienda')">TIENDA</a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Props
defineProps({
  scrollTo: {
    type: Function,
    required: true
  }
})

// Reactive data
const isScrolled = ref(false)

// Methods
const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

// Lifecycle
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Navigation */
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 12px 0;
  background: #F5F5F0;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  border-bottom: 3px solid #000000;
}

.nav-scrolled {
  background: rgba(245, 245, 240, 0.95);
  backdrop-filter: blur(10px);
  padding: 8px 0;
  border-bottom: 3px solid #000000;
}

.nav-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand {
  display: flex;
  align-items: center;
}

.nav-brand-link {
  display: flex;
  align-items: center;
  gap: 12px;
  transition: all 0.3s ease;
}

.nav-brand-link:hover {
  transform: scale(1.05);
  opacity: 0.9;
}

.nav-logo {
  height: 45px;
  width: auto;
  transition: all 0.3s ease;
  filter: brightness(0.2) contrast(1.1);
}

.nav-scrolled .nav-logo {
  height: 35px;
}

.nav-menu {
  display: flex;
  gap: 40px;
}

.nav-menu a {
  color: #1A1A1A;
  text-decoration: none;
  font-weight: 700;
  font-size: 0.9rem;
  letter-spacing: 1px;
  transition: all 0.3s ease;
  position: relative;
}

.nav-menu a:hover {
  color: #000000;
  transform: translateY(-2px);
}

.nav-menu a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: #000000;
  transition: width 0.3s ease;
}

.nav-menu a:hover::after {
  width: 100%;
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
}

@media (max-width: 480px) {
  .nav-menu {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style> 