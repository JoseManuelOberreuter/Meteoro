# METEORO - Sitio Web

Sitio web desarrollado para METEORO, un sello discográfico innovador. El proyecto está construido con Vue 3 y diseñado con un enfoque en animaciones fluidas y una experiencia de usuario moderna.

## 🛠️ Tecnologías Utilizadas

- **Vue 3**: Framework principal
- **Vite**: Build tool y servidor de desarrollo
- **CSS Puro**: Diseño y animaciones personalizadas sin frameworks externos
- **Responsive Design**: Adaptable a todos los dispositivos

## 📂 Estructura del Proyecto

```
METEORO/
├── src/
│   ├── App.vue           # Componente principal con toda la UI
│   ├── assets/           # Recursos estáticos
│   └── main.js           # Punto de entrada
├── public/               # Archivos públicos
├── dist/                 # Build de producción
└── package.json         # Dependencias y scripts
```

## 🎨 Características Principales

### Diseño
- Diseño minimalista y moderno
- Paleta de colores:
  - Negro (`#1A1A1A`)
  - Blanco (`#F3F0EA`)
  - Amarillo Neón (`#F9FF45`)
  - Azul Eléctrico (`#3366CC`)
  - Rojo Saturado (`#F73939`)
- Tipografía principal: Arial Black
- Animaciones suaves y responsivas

### Secciones
1. **Hero**: Animación de texto por líneas con efecto de entrada
2. **Artistas**: Grid responsivo con hover effects
3. **Sesiones**: Galería de videos con overlay interactivo
4. **Sobre Nosotros**: Sección con estadísticas animadas
5. **Contacto**: Formularios y enlaces sociales interactivos

### Componentes Destacados
- Navegación con efecto de scroll
- Marquee animado con CSS puro
- Cards con efectos de hover
- Formas geométricas animadas en el fondo
- Botones con efectos de brillo

## 🚀 Instalación y Desarrollo

1. Clonar el repositorio:
```bash
git clone https://github.com/JoseManuelOberreuter/Meteoro.git
cd Meteoro
```

2. Instalar dependencias:
```bash
npm install
```

3. Iniciar servidor de desarrollo:
```bash
npm run dev
```

4. Construir para producción:
```bash
npm run build
```

## 📱 Responsive Design

El sitio está optimizado para:
- Escritorio (1200px+)
- Tablet (768px - 1199px)
- Móvil (< 768px)

## 🔧 Personalización

### Colores
Los colores principales se pueden modificar en `src/App.vue`:
```css
:root {
  --black: #1A1A1A;
  --white: #F3F0EA;
  --neon-yellow: #F9FF45;
  --electric-blue: #3366CC;
  --saturated-red: #F73939;
}
```

### Animaciones
Las animaciones principales incluyen:
- Efecto de float para elementos de fondo
- Slide para el marquee
- Fade in para textos
- Hover effects en cards y botones

## 📝 Notas de Desarrollo

- Implementación de scroll suave para navegación
- Optimización de rendimiento en animaciones
- Uso de CSS Grid para layouts responsivos
- Implementación de efectos visuales sin librerías externas

## 👨‍💻 Desarrollador

Desarrollado por José Manuel Oberreuter
- [GitHub](https://github.com/JoseManuelOberreuter)

---

### 🎵 METEORO - Más que música, somos impacto.