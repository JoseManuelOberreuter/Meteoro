<template>
  <div id="app">
    <!-- Navigation -->
    <NavBar :scrollTo="scrollTo" />

    <!-- Hero Section -->
    <HeroSection :scrollTo="scrollTo" />

    <!-- Artists Section -->
    <ArtistsSection />

    <!-- Marquee Section -->
    <MarqueeSection text="LOREM IPSUM DOLOR SIT AMET • CONSECTETUR ADIPISCING • ELIT SED DO EIUSMOD" />

    <!-- Sessions Section -->
    <SessionsSection />

    <!-- About Section -->
    <AboutSection />

    <!-- Team Section -->
    <TeamSection />

    <!-- Green Marquee Section -->
    <MarqueeSection text="DESCUBRE • INNOVA • TRANSFORMA • IMPACTA • EVOLUCIONA" :isGreen="true" />

    <!-- News Section -->
    <NewsSection />

    <!-- Contact Section -->
    <ContactSection />

    <!-- Store Section -->
    <StoreSection />
    
    <!-- Footer -->
    <FooterSection />
  </div>
</template>

<script setup>
// Import all components
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ArtistsSection from './components/ArtistsSection.vue'
import MarqueeSection from './components/MarqueeSection.vue'
import SessionsSection from './components/SessionsSection.vue'
import AboutSection from './components/AboutSection.vue'
import TeamSection from './components/TeamSection.vue'
import NewsSection from './components/NewsSection.vue'
import ContactSection from './components/ContactSection.vue'
import StoreSection from './components/StoreSection.vue'
import FooterSection from './components/FooterSection.vue'

// Methods
const scrollTo = (elementId) => {
  const element = document.getElementById(elementId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style>
/* Only minimal styles needed for the main app container */
#app {
  min-height: 100vh;
}
</style>