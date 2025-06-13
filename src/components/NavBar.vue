<template>
  <nav class="nav" :class="{ 'nav-scrolled': isScrolled }">
    <div class="nav-container">
      <div class="nav-brand">
        <a href="#" @click.prevent="scrollTo('app')" class="nav-brand-link">
          <img src="@/assets/Sin Fondo_ISOTIPO BLANCO.png" alt="METEORO Isotipo" class="nav-isotipo">
          <img src="@/assets/Sin Fondo-LOGOTIPO BLANCO.png" alt="METEORO" class="nav-logotipo">
        </a>
      </div>
      <div class="nav-menu">
        <a href="#artistas" @click="scrollTo('artistas')">ARTISTAS</a>
        <a href="#catalogo" @click="scrollTo('catalogo')">CATÁLOGO</a>
        <a href="#sobre" @click="scrollTo('sobre')">SOBRE NOSOTRXS</a>
        <a href="#noticias" @click="scrollTo('noticias')">NOTICIAS</a>
        <a href="#contacto" @click="scrollTo('contacto')">CONTACTO</a>
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

.nav-isotipo {
  height: 60px;
  width: auto;
  transition: all 0.3s ease;
  filter: brightness(1.1) contrast(1.1);
}

.nav-logotipo {
  height: 40px;
  width: auto;
  transition: all 0.3s ease;
  filter: brightness(1.1) contrast(1.1);
}

.nav-scrolled .nav-isotipo {
  height: 45px;
  filter: brightness(1.2) contrast(1.2);
}

.nav-scrolled .nav-logotipo {
  height: 30px;
  filter: brightness(1.2) contrast(1.2);
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