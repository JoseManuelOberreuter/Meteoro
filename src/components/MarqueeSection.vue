<template>
  <section class="marquee-section" :class="{ 'green-marquee': isGreen }">
    <div class="marquee-container">
      <div class="marquee-track">
        <div class="marquee-item">{{ text }}</div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Props
defineProps({
  text: {
    type: String,
    default: 'LOREM IPSUM DOLOR SIT AMET • CONSECTETUR ADIPISCING • ELIT SED DO EIUSMOD'
  },
  isGreen: {
    type: Boolean,
    default: false
  }
})
</script>

<style scoped>
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