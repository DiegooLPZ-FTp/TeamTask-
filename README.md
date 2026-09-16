# Team Task 🚀

Sistema integral de gestión colaborativa de tareas para equipos académicos, startups y pequeñas empresas.

## ✨ Características Principales

- ✅ **Asignación Inteligente**: Considera habilidades, disponibilidad y carga actual
- ✅ **Métricas Reales**: Visualiza porcentaje de participación de cada miembro
- ✅ **Comunicación Integrada**: Chat y comentarios centralizados en plataforma
- ✅ **Notificaciones Automáticas**: Recordatorios en tiempo real (máx 5 segundos)
- ✅ **Adjuntos Organizados**: PDF, Word, Excel, imágenes, PowerPoint, videos, audios
- ✅ **Historial Auditable**: Quién hizo qué y cuándo (audit trail completo)
- ✅ **Reportes Automáticos**: Análisis diarios y semanales
- ✅ **Role-based Access**: Permisos por rol (Líder, Miembro, Admin)

## 🛠 Tech Stack

### Frontend
- **React 18+** con TypeScript
- **Vite** (bundler extremadamente rápido)
- **Tailwind CSS** (utility-first CSS)
- **Zustand/Redux** (state management)
- **Axios** (HTTP client)
- **Socket.io-client** (real-time communication)

### Backend
- **Node.js** runtime
- **Express.js** (web framework)
- **TypeScript** (static typing)
- **PostgreSQL** (base de datos robusta)
- **Prisma ORM** (database toolkit)
- **Redis** (caché y sesiones)
- **Socket.io** (real-time messaging)
- **JWT** (autenticación)

### DevOps & Testing
- **Docker** + **Docker-Compose** (containerización)
- **GitHub Actions** (CI/CD automatizado)
- **Vitest** (testing framework)
- **ESLint** + **Prettier** (code quality)

## 📋 Requisitos Previos

- **Node.js** 18.0.0 o superior
- **npm** 8.0.0 o superior
- **PostgreSQL** 12 o superior
- **Redis** 6 o superior
- **Docker** (opcional, para desarrollo con contenedores)

## 🚀 Quick Start

### 1. Clonar Repositorio

```bash
git clone https://github.com/DiegooLPZ-FTp/TeamTask-.git
cd TeamTask-
```

### 2. Setup Frontend

```bash
cd frontend
npm install
cp .env.example .env
npm run dev
```

**Accede a:** http://localhost:3000

### 3. Setup Backend

```bash
cd ../backend
npm install
cp .env.example .env
npm run dev
```

**Accede a:** http://localhost:5000/api

### 4. Setup Base de Datos

```bash
cd backend
npx prisma migrate dev --name init
npx prisma generate
```

### 5. Con Docker Compose (Recomendado)

```bash
# Desde la raíz del proyecto
docker-compose up -d
```

Esto levanta:
- PostgreSQL en puerto 5432
- Redis en puerto 6379
- Backend en puerto 5000
- Frontend en puerto 3000

## 📚 Documentación

- **[Setup Detallado](./docs/SETUP.md)** - Guía completa de instalación
- **[API Reference](./docs/API.md)** - Especificación de endpoints REST
- **[Database Schema](./docs/DATABASE.md)** - Diseño de base de datos
- **[Architecture](./docs/ARCHITECTURE.md)** - Arquitectura del sistema
- **[Contributing Guide](./docs/CONTRIBUTING.md)** - Guía para contribuidores

## 📊 Documentación Académica

- **[1er Parcial - Documento Completo](./docs/Team_Task_Entrega_1er_Parcial_CON_DIAGRAMAS.docx)**
  - Casos de Uso
  - Diagrama de Clases
  - Modelo de Relaciones
  - Glosario del Sistema
  - Requisitos (28 RF + 17 RNF)

## 👥 Equipo de Desarrollo

| Nombre | Rol |
|--------|-----|
| Diego Alberto López Montes | Developer |
| Álvaro Gael García Ramírez | Developer |
| Christopher Mauricio Cuevas Medina | Developer |
| José Alexander de la Rosa | Developer |

## 🎓 Información Académica

- **Universidad:** Universidad Autónoma de Aguascalientes
- **Materia:** Análisis y Diseño de Sistemas (Grupo 5-B)
- **Profesor:** Erwin Brian Montes Chaparro
- **Período:** Agosto - Diciembre 2026

## 🤝 Contribuir

Queremos tu ayuda para mejorar Team Task. Sigue estos pasos:

1. **Fork** el repositorio
2. **Crea una rama** para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit tus cambios** (`git commit -m 'feat: Add AmazingFeature'`)
4. **Push a la rama** (`git push origin feature/AmazingFeature`)
5. **Abre un Pull Request**

Ver [CONTRIBUTING.md](./docs/CONTRIBUTING.md) para más detalles.

### Convención de Commits

```
feat(scope): descripción       - Nueva característica
fix(scope): descripción        - Arreglo de bug
docs(scope): descripción       - Documentación
style(scope): descripción      - Formato/estilos
refactor(scope): descripción   - Refactorización
test(scope): descripción       - Tests
chore(scope): descripción      - Tareas generales
```

## 📝 Scripts Disponibles

### Root Level
```bash
npm run setup        # Instala todas las dependencias
npm run dev          # Inicia frontend y backend simultáneamente
npm run build        # Construye frontend y backend
npm run test         # Ejecuta tests en ambos
npm run docker       # Levanta los contenedores
npm run docker-down  # Para los contenedores
```

### Backend
```bash
npm run dev          # Servidor en desarrollo
npm run build        # Build para producción
npm run start        # Ejecutar servidor
npm run test         # Tests con Vitest
npm run lint         # Verificar código con ESLint
npm run migrate      # Ejecutar migraciones Prisma
npm run seed         # Poblar base de datos (si existe)
```

### Frontend
```bash
npm run dev          # Servidor Vite en desarrollo
npm run build        # Build optimizado
npm run preview      # Preview del build
npm run test         # Tests con Vitest
npm run lint         # Verificar código
```

## 🐛 Reportar Bugs

Encontraste un bug? Por favor abre un [issue](https://github.com/DiegooLPZ-FTp/TeamTask-/issues/new?template=bug.md) con:
- Descripción clara del problema
- Pasos para reproducir
- Comportamiento esperado
- Comportamiento actual
- Sistema operativo y versión

## 💡 Sugerir Features

Tienes una idea? Abre un [issue](https://github.com/DiegooLPZ-FTp/TeamTask-/issues/new?template=feature.md) con:
- Descripción de la feature
- Justificación
- Beneficios
- Ejemplos de uso

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Ver [LICENSE](./LICENSE) para más detalles.

## 📞 Contacto

¿Preguntas o sugerencias?
- Abre un [issue](https://github.com/DiegooLPZ-FTp/TeamTask-/issues)
- Contacta al equipo en los issues
- Revisa [Discussions](https://github.com/DiegooLPZ-FTp/TeamTask-/discussions)

---

<div align="center">

**Estado del Proyecto**

| Fase | Estado | Fecha |
|------|--------|-------|
| 1er Parcial | ✅ Completado | Sept 2026 |
| 2do Parcial | 🚧 En Desarrollo | Oct 2026 |
| 3er Parcial | 📋 Planeado | Nov 2026 |
| 4to Parcial | 📋 Planeado | Dic 2026 |

Última actualización: **15 de Septiembre de 2026** -VS Code Test

</div>


## ✅ Configuración de VS Code Completada

- Cuenta GitHub conectada correctamente
- Git configurado con usuario y email
- Listo para comenzar desarrollo