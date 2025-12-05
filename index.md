# Melodía — Bitácora Final del Proyecto

Bienvenidos a la bitácora final del proyecto **Melodía**, una plataforma musical modular construida bajo un esquema de microservicios, con frontend móvil, frontend web, backoffice administrativo y servicios backend independientes.

Este sitio documenta las decisiones técnicas, arquitectura, problemas encontrados, mejoras pendientes y conclusiones del proyecto.

---

## 📌 Contenidos

- [Arquitectura del Sistema](arquitectura.md)
- [Decisiones Técnicas](decisiones.md)
- [Problemas y Lecciones Aprendidas](problemas.md)
- [Funcionalidades Incompletas / Mejoras Pendientes](incompletas.md)
- [Features Destacadas](features.md)

---

## 🧩 Descripción General del Proyecto

Melodía es una plataforma musical completa con:

- Aplicación móvil (React Native / Expo)
- Web App para usuarios
- Backoffice administrativo
- Microservicios independientes:
  - **melody-auth** (Java + Spring Boot) — Autenticación centralizada
  - **music-manager** (Node/NestJS) — Gestión de canciones, álbumes, géneros y uploads
  - **users-manager** (Node/NestJS) — Usuarios, perfiles, conexiones sociales
  - **BFF** (Node/NestJS) — Puerta de entrada unificada
- Persistencia:
  - **MongoDB** para canciones y playlists
  - **Postgres** para usuarios
  - **Firebase Storage** para archivos de audio

Cada servicio está contenerizado vía Docker, con pipeline CI/CD vía GitHub Actions y análisis de cobertura con Codecov.

---

## 👥 Equipo y Responsabilidades

### **Frontend – Julián Mutchinick**
- UI completa de la plataforma
- Home, playlists, historial, navegación y UX
- Reproductor musical
- Perfiles de artista y usuario
- Búsqueda unificada
- Cola de reproducción

### **Full Stack – Gonzalo Calderón**
- Recuperación de contraseña
- Validación de tokens y guards
- Picks destacados, artistas relacionados
- Feed social, compartir contenido
- Subida de canciones
- Monitoreo y fixes de checkpoint anterior

### **Backend – Lucas Correa**
- Desarrollo del microservicio **music-manager**
- MongoDB + Firebase Storage
- Creación de canciones, álbumes
- Onboarding: géneros y artistas
- Integración con BFF y melody-auth

### **Backend – Gonzalo Toyos**
- Sistema de followers
- Colaboraciones
- Actividades recientes
- Playlists y carrusel de fotos
- Backend del feed social

### **Backend / Backoffice – Mateo Ibáñez**
- Panel administrativo completo
- Gestión avanzada de usuarios
- Canciones populares, rankings, métricas
- Búsqueda unificada
- Sistema de likes
- Tracking de reproducciones

---

Este sitio reúne toda la documentación necesaria para comprender cómo está construido el proyecto y qué decisiones se tomaron.
