<template>
  <nav class="nav" :class="{ 'nav-scrolled': isScrolled }">
    <div class="nav-container">
      <div class="nav-brand">
        <a href="#" @click.prevent="scrollTo('app')" class="nav-brand-link">
          <img src="@/assets/LOGO HEADER METEORO.png" alt="METEORO Logo" class="nav-logo">
        </a>
      </div>
      
      <!-- Desktop Menu -->
      <div class="nav-menu desktop-menu">
        <a href="#artistas" @click="scrollTo('artistas')">ARTISTAS</a>
        <a href="#catalogo" @click="scrollTo('catalogo')">LANZAMIENTOS</a>
        <a href="#equipo" @click="scrollTo('equipo')">NOSOTRXS</a>
        <a href="#tienda" @click="scrollTo('tienda')">TIENDA</a>
      </div>

      <!-- Mobile Hamburger Button -->
      <button 
        class="hamburger-button" 
        @click="toggleMobileMenu"
        :class="{ 'active': isMobileMenuOpen }"
        aria-label="Toggle mobile menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>

    <!-- Mobile Fullscreen Menu -->
    <div class="mobile-menu-overlay" :class="{ 'active': isMobileMenuOpen }">
      <div class="mobile-menu">
        <button 
          class="close-button"
          @click="toggleMobileMenu"
          aria-label="Close mobile menu"
        >
          ×
        </button>
        
        <div class="mobile-menu-content">
          <a href="#artistas" @click="handleMobileMenuClick('artistas')" class="mobile-menu-item">
            ARTISTAS
          </a>
          <a href="#catalogo" @click="handleMobileMenuClick('catalogo')" class="mobile-menu-item">
            LANZAMIENTOS
          </a>
          <a href="#equipo" @click="handleMobileMenuClick('equipo')" class="mobile-menu-item">
            NOSOTRXS
          </a>
          <a href="#tienda" @click="handleMobileMenuClick('tienda')" class="mobile-menu-item">
            TIENDA
          </a>
        </div>
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
const isMobileMenuOpen = ref(false)

// Methods
const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
  
  // Prevent body scroll when menu is open
  if (isMobileMenuOpen.value) {
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = ''
  }
}

const handleMobileMenuClick = (section) => {
  scrollTo(section)
  toggleMobileMenu()
}

// Close mobile menu on escape key
const handleKeydown = (e) => {
  if (e.key === 'Escape' && isMobileMenuOpen.value) {
    toggleMobileMenu()
  }
}

// Lifecycle
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  document.addEventListener('keydown', handleKeydown)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  document.removeEventListener('keydown', handleKeydown)
  // Clean up body overflow on unmount
  document.body.style.overflow = ''
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
  border-bottom: 4px solid #000000;
}

.nav-scrolled {
  background: rgba(245, 245, 240, 0.95);
  backdrop-filter: blur(10px);
  padding: 8px 0;
  border-bottom: 4px solid #000000;
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

/* Hamburger Button */
.hamburger-button {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: 10px;
  z-index: 1001;
  transition: opacity 0.3s ease;
}

.hamburger-button.active {
  opacity: 0;
  pointer-events: none;
}

.hamburger-button span {
  display: block;
  width: 25px;
  height: 3px;
  background: #1A1A1A;
  margin: 3px 0;
  transition: all 0.3s ease;
  transform-origin: center;
}

.hamburger-button.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.hamburger-button.active span:nth-child(2) {
  opacity: 0;
}

.hamburger-button.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* Mobile Menu Overlay */
.mobile-menu-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background: rgba(245, 245, 240, 0.98);
  backdrop-filter: blur(10px);
  z-index: 999;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}

.mobile-menu-overlay.active {
  opacity: 1;
  visibility: visible;
}

.mobile-menu {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
}

.close-button {
  position: absolute;
  top: 30px;
  right: 30px;
  background: none;
  border: none;
  font-size: 3rem;
  color: #1A1A1A;
  cursor: pointer;
  z-index: 1002;
  transition: all 0.3s ease;
}

.close-button:hover {
  color: #000000;
  transform: scale(1.1);
}

.mobile-menu-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3rem;
  padding: 2rem;
}

.mobile-menu-item {
  color: #1A1A1A;
  text-decoration: none;
  font-weight: 700;
  font-size: 2rem;
  letter-spacing: 2px;
  transition: all 0.3s ease;
  text-align: center;
  position: relative;
}

.mobile-menu-item:hover {
  color: #000000;
  transform: scale(1.05);
}

.mobile-menu-item::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 3px;
  background: #000000;
  transition: width 0.3s ease;
}

.mobile-menu-item:hover::after {
  width: 100%;
}

/* Responsive Design */
@media (max-width: 768px) {
  .nav-container {
    padding: 0 20px;
  }
  
  .desktop-menu {
    display: none;
  }
  
  .hamburger-button {
    display: flex;
  }
  
  .nav-logo {
    height: 40px;
  }
  
  .nav-scrolled .nav-logo {
    height: 30px;
  }
}

@media (max-width: 480px) {
  .nav-container {
    padding: 0 15px;
  }
  
  .mobile-menu-item {
    font-size: 1.5rem;
  }
  
  .mobile-menu-content {
    gap: 2rem;
  }
  
  .close-button {
    font-size: 2.5rem;
    top: 20px;
    right: 20px;
  }
}
</style> 