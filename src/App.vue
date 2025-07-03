<template>
  <div id="app">
    <!-- Navigation -->
    <NavBar :scrollTo="scrollTo" />

    <!-- Artists Section -->
    <ArtistsSection />

    <!-- Sessions Section -->
    <SessionsSection />

    <!-- Team Section -->
    <TeamSection />

    <!-- Store Section -->
    <StoreSection />
    
    <!-- Footer -->
    <FooterSection />
  </div>
</template>

<script setup>
// Import all components
import NavBar from './components/NavBar.vue'
import ArtistsSection from './components/ArtistsSection.vue'
import SessionsSection from './components/SessionsSection.vue'
import TeamSection from './components/TeamSection.vue'
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