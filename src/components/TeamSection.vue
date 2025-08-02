<template>
  <section id="equipo" class="team-section">
    <div class="section-container">
      <div class="team-content">
        <div class="team-text">
          <h2 class="section-title">SOBRE NOSOTRXS</h2>
          <p>
            Meteoro es un sello independiente chileno que impulsa proyectos musicales de forma integral, abarcando desde la puesta en escena y el sonido en vivo hasta la identidad visual y el desarrollo artístico.
          </p>
          <p>
            Nos enfocamos en la creación de contenido audiovisual y dirección de arte para construir identidades sólidas, conectar con audiencias y posicionar a lxs artistas en la industria.
          </p>
          <p>
            Promovemos una creación colaborativa, distribución justa de beneficios y un acompañamiento estratégico constante.
          </p>
          <p>
            Buscamos ser una plataforma creativa que reuna música, arte, gestión cultural y comunidad, con un compromiso firme hacia la cultura local y latinoamericana.
          </p>
        </div>
        <div class="team-visual">
          <div class="team-image">
            <img src="@/assets/SELLO METEORO 5_1.jpg" alt="Nuestro Equipo METEORO" class="team-photo">
          </div>
          <p class="team-description">Equipo meteoro; de izquierda a derecha Dani, Stefa y Jaque</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// This component doesn't need any JavaScript logic
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
  text-align: left;
  margin-bottom: 80px;
  letter-spacing: -1px;
  color: var(--black);
  border-bottom: 5px solid #000000;
    display: inline-block;
}

/* Team Section */
.team-section {
  padding: 120px 0;
  background: #F5F5F0;
}

.team-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: start;
}

.team-text {
  color: #1A1A1A;
}

.team-text .section-title {
  color: #1A1A1A;
  text-align: left;
  margin-bottom: 40px;
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  border-bottom: 5px solid #000000;
  display: inline-block;
}

.team-text p {
  font-size: 1.3rem;
  line-height: 1.6;
  margin-bottom: 30px;
  opacity: 0.9;
  text-align: justify;
}

.team-visual {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  margin-top: 20px;
}

.team-image {
  position: relative;
  overflow: hidden;
  transition: all 0.4s ease;
  width: 100%;
  max-width: 600px;
  border: 5px solid #000000;
}

.team-image:hover {
  transform: translateY(-10px);
}

.team-photo {
  width: 100%;
  height: auto;
  display: block;
  transition: all 0.4s ease;
}

.team-image:hover .team-photo {
  transform: scale(1.05);
}

.team-description {
  text-align: center;
  margin-top: 20px;
  font-size: 1.1rem;
  color: #666;
  font-style: italic;
  line-height: 1.4;
}

/* Responsive Design */
@media (max-width: 768px) {
  .section-container {
    padding: 0 20px;
  }
  
  .team-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}
</style> 