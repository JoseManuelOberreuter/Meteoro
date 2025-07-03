<template>
  <section id="equipo" class="team-section">
    <div class="section-container">
      <div class="team-content">
        <div class="team-text">
          <h2 class="section-title">SOBRE NOSOTRXS</h2>
          <p>
            Somos una discográfica independiente fundada en Santiago de Chile.
          </p>
          <p>
            Buscamos impulsar proyectos musicales de manera integral, abarcando puesta en escena, sonido, identidad visual y otros aspectos clave para su desarrollo dentro de la industria.
          </p>
          <p>
            El corazón de Meteoro está en la generación de material audiovisual y la dirección de arte de los proyectos. Creemos que una identidad visual sólida y coherente es clave para conectar con nuevas audiencias, consolidar la presencia de los artistas en la industria y hacerlos parte de escenarios relevantes.
          </p>
        </div>
        <div class="team-visual">
          <div class="team-image">
            <img src="@/assets/SELLO METEORO 5_1.jpg" alt="Nuestro Equipo METEORO" class="team-photo">
          </div>
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
  padding-bottom: 10px;
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
  align-items: center;
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
  padding-bottom: 10px;
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
  justify-content: center;
  align-items: center;
  width: 100%;
}

.team-image {
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  transition: all 0.4s ease;
  width: 100%;
  max-width: 600px;
}

.team-image:hover {
  transform: translateY(-10px);
  box-shadow: 0 30px 80px rgba(0, 0, 0, 0.4);
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