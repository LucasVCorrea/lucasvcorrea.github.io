# 🧯 Problemas Encontrados y Lecciones Aprendidas

---

## 🐞 Problemas encontrados

### 1. Sincronización entre BFF y microservicios
Hubo inconsistencias en contratos entre servicios, solucionado con DTOs compartidos del monorepo.

### 2. Dificultad con Firebase Storage
Problemas de permisos y uploads simultáneos.

### 3. Estados inconsistentes en mobile
El reproductor requería manejar múltiples fuentes y eventos a la vez.

### 4. Testing E2E lento
Se resolvió usando docker-compose y bases de datos aisladas.

---

## 📘 Lecciones aprendidas

- La autenticación centralizada simplifica todo
- MongoDB es perfecto para catálogos flexibles
- Postgres continúa siendo ideal para relaciones complejas
- Docker debe usarse desde el inicio
- Los contratos entre microservicios deben estar muy claros
- El BFF simplifica la complejidad del ecosistema
