# 🏗️ Arquitectura del Sistema

Este documento describe la arquitectura general de Melodía, sus microservicios, tecnologías utilizadas y las decisiones técnicas que guiaron el diseño del sistema.

---

## 📡 Diagramas de Arquitectura

A continuación se muestra un carrusel de diagramas que representan diferentes vistas de la arquitectura del sistema.  
Podés recorrerlos usando los indicadores inferiores.

<div class="carousel-container">
  <div class="carousel">

    <!-- Slide 1 -->
    <input type="radio" name="slides" id="slide-1" checked>
    <label for="slide-1" class="carousel__nav"></label>
    <figure>
      <img src="/assets/arquitectura.png" />
      <figcaption>Arquitectura General del Sistema</figcaption>
    </figure>

    <!-- Slide 2 -->
    <input type="radio" name="slides" id="slide-2">
    <label for="slide-2" class="carousel__nav"></label>
    <figure>
      <img src="/assets/diagrama-flujo-playlist.png" />
      <figcaption>Flujo: Creación de Playlists</figcaption>
    </figure>

    <!-- Slide 3 -->
    <input type="radio" name="slides" id="slide-3">
    <label for="slide-3" class="carousel__nav"></label>
    <figure>
      <img src="/assets/microservicios.png" />
      <figcaption>Distribución de Microservicios</figcaption>
    </figure>

  </div>
</div>

<style>
.carousel-container {
  width: 100%;
  max-width: 900px;
  margin: auto;
  position: relative;
}

.carousel {
  position: relative;
  overflow: hidden;
  border-radius: 10px;
  padding-bottom: 40px;
}

.carousel input {
  display: none;
}

.carousel figure {
  display: none;
  margin: 0;
}

.carousel img {
  width: 100%;
  border-radius: 8px;
}

.carousel figcaption {
  text-align: center;
  font-size: 0.9rem;
  color: #555;
  margin-top: 6px;
}

#slide-1:checked ~ figure:nth-of-type(1),
#slide-2:checked ~ figure:nth-of-type(2),
#slide-3:checked ~ figure:nth-of-type(3) {
  display: block;
}

.carousel__nav {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  display: inline-block;
  margin: 8px 4px;
  background: #ccc;
  cursor: pointer;
  position: relative;
  top: -12px;
}

input#slide-1:checked ~ label[for="slide-1"],
input#slide-2:checked ~ label[for="slide-2"],
input#slide-3:checked ~ label[for="slide-3"] {
  background: #4a90e2;
}
</style>

---

# 🧠 Decisiones de Arquitectura

A lo largo del desarrollo se tomaron decisiones claves que dieron forma al sistema. Estas son las más importantes:

---

## 1. **Separación en Microservicios**

Melodía no es un monolito, sino un ecosistema modular compuesto por servicios independientes:

- **melody-auth** (Java + Spring Boot)  
  → Autenticación centralizada, gestión de tokens, login, verificación de credenciales y sesiones.

- **music-manager** (Node + NestJS + MongoDB + Firebase Storage)  
  → Gestión de canciones, álbumes, géneros, subida de archivos.

- **users-manager** (Node + NestJS + Postgres)  
  → Manejo de usuarios, perfiles, follows, configuraciones.

- **BFF (Backend for Frontend)**  
  → Capa intermedia para unificar entrada desde web + mobile y simplificar al frontend.

### ¿Por qué microservicios?

- El equipo podía trabajar en paralelo.  
- Escalabilidad independiente.  
- Flexibilidad tecnológica por servicio.  
- Aislamiento de errores.

---

## 2. **Elección de Tecnologías**

### **Java + Spring Boot para Autenticación**
- Robustez para validación de tokens.
- Integración madura con JWT.
- Ideal para lógica crítica.

### **Node + NestJS para la mayoría de los servicios**
- Arquitectura modular.
- DX excelente.
- Curva de aprendizaje rápida para el equipo.

### **MongoDB para música / metadatos**
- Ideal para documentos jerárquicos.
- Lecturas rápidas.

### **PostgreSQL para usuarios**
- Integridad y relaciones.

### **Firebase Storage**
- Hosting escalable y económico.
- Ideal para manejo de multimedia.

---

## 3. **BFF como puerta de entrada**

Ventajas:

- Centraliza validación de tokens.
- Unifica los endpoints para frontend.
- Permite enriquecer respuestas.
- Oculta complejidad interna.

---

## 4. **CI/CD & Contenedores**

- **Docker** para portabilidad.
- **GitHub Actions** para automatización.
- **Codecov** para calidad de código.

---

## 5. **Modelo orientado a eventos (Diseñado, no implementado)**

- Eventos clave: playlist creada, usuario registrado, música subida.
- Facilita estadísticas y recomendaciones.
- Aísla lógicas entre servicios.

---

## 6. **Frontends independientes**

- Web App (React)
- Mobile (React Native)
- Backoffice (React)

---
