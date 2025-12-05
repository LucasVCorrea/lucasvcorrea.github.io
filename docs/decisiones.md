# 🧠 Decisiones Técnicas y de Arquitectura

---

## 🧩 Por qué microservicios

- Split natural entre dominios: usuarios, música, catálogo, autenticación
- Permite escalar servicios por separado
- Equipos independientes trabajando en paralelo
- Deploy aislado por servicio

---

## 🔒 Autenticación centralizada (melody-auth)

Se decidió separar el servicio de autenticación para:

- Evitar duplicación de lógica entre microservicios
- Tener un sistema homogéneo de tokens
- Aislar credenciales y verificación
- Permitir reemplazo sin afectar al resto del sistema

---

## 🗃️ Por qué MongoDB para música

- Estructuras flexibles (álbumes, playlists)
- Documentos embebidos → performance en lecturas
- Escalabilidad horizontal natural

---

## 🗃️ Por qué Postgres para usuarios

- Modelo relacional ideal para followers, permisos y métricas
- Consultas complejas con JOINs
- Integridad referencial

---

## 🗂️ Por qué Firebase Storage

- Solución simple, barata y escalable para archivos de audio
- CDN integrado
- SDK first-class para Node

---

## 🛠️ Stack de Testing

- **Node/NestJS:** Jest → unit, e2e, coverage  
- **Java:** Maven + JUnit  
- **Integración:** docker-compose para entornos reales

---

## 🐳 Por qué Docker

- Entornos aislados
- Tests reproducibles
- Deploy simplificado a Google Cloud

---

## 🚀 GitHub Actions + Codecov

- Workflows para:
  - Lint + build
  - Tests unitarios y E2E
  - Análisis de coverage con Codecov
  - Build y push de imágenes Docker
- Automatización del pipeline sin complejidad adicional
