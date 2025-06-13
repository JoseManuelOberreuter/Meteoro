<template>
  <section id="noticias" class="news-section">
    <div class="section-container">
      <h2 class="section-title">NOTICIAS</h2>
      <div class="news-list">
        <article 
          v-for="article in news" 
          :key="article.id" 
          class="news-item"
        >
          <span class="news-date">{{ article.date }}</span>
          <h3 class="news-title">{{ article.title }}</h3>
          <p class="news-excerpt">{{ article.excerpt }}</p>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
import { news } from '@/data/news.js'
</script>

<style scoped>
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

/* News Section */
.news-section {
  padding: 120px 0;
  background: var(--neon-yellow);
}

.news-section .section-title {
  color: var(--black);
}

.news-list {
  display: flex;
  flex-direction: column;
  gap: 40px;
  margin-top: 60px;
}

.news-item {
  padding: 30px;
  background: var(--black);
  border-radius: 10px;
  transition: all 0.3s ease;
}

.news-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.news-date {
  font-size: 0.9rem;
  font-weight: 700;
  color: var(--neon-yellow);
  letter-spacing: 1px;
  margin-bottom: 15px;
  display: block;
}

.news-title {
  font-size: 1.5rem;
  font-weight: 900;
  margin-bottom: 15px;
  color: var(--white);
  line-height: 1.3;
}

.news-excerpt {
  font-size: 1rem;
  line-height: 1.6;
  color: var(--white);
  opacity: 0.9;
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .news-list {
    gap: 30px;
  }
  
  .news-item {
    padding: 20px;
  }
}
</style> 