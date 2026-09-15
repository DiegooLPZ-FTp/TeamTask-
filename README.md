# Team Task

Sistema de Gestión Colaborativa de Tareas para Equipos

---

## Descripción

Team Task es una plataforma diseñada para equipos universitarios, emprendimientos y pequeñas empresas que necesitan organizar, distribuir y medir el trabajo de forma equitativa.

**Concepto Principal:**

> Equidad ≠ Igualdad
> 
> Distribuir trabajo considerando habilidades, complejidad y disponibilidad de cada miembro.

---

## Componentes del Sistema

El sistema se estructura en cinco pilares fundamentales:

1. **Asignar** - Distribución inteligente de tareas considerando competencias disponibles
2. **Calendarizar** - Programación flexible con deadlines definidos
3. **Notificar** - Alertas en tiempo real (máximo 5 segundos)
4. **Medir** - Métricas detalladas de participación
5. **Reportar** - Análisis exportables a PDF y Excel

---

## Funcionalidades

- Asignación inteligente de tareas basada en skills y disponibilidad
- Gestión de proyectos colaborativa en tiempo real
- Registro y monitoreo de competencias por miembro
- Notificaciones instantáneas y chat integrado
- Análisis de carga de trabajo y balance de equipo
- Reportes automáticos (diarios y semanales)
- Auditoría completa de cambios
- Interfaz responsive para web y dispositivos móviles

---

## Stack Tecnológico

**Frontend:** React 18+, TypeScript, Vite, Tailwind CSS, Zustand/Redux, React Router, Socket.io-client, Axios

**Backend:** Node.js, Express.js, TypeScript, Prisma ORM, Socket.io, JWT, Redis

**Database:** PostgreSQL, Redis

**Infraestructura:** Docker, Docker Compose, GitHub Actions

**Testing:** Vitest, ESLint, Prettier

---

## Requisitos

**Funcionales (28):** Gestión de usuarios y autenticación. Administración de proyectos y equipos. Creación y asignación inteligente de tareas. Registro de competencias. Notificaciones, chat integrado y auditoría. Reportes automáticos con análisis de participación y desempeño.

**No-Funcionales (17):** Respuesta del sistema menor a 2 segundos. Disponibilidad 99%. Escalabilidad para 1000+ usuarios simultáneos. Compatibilidad con navegadores modernos. Diseño responsive. Seguridad con encriptación y auditoría completa. Backups automáticos diarios.

---

## Instalación

**Prerrequisitos:** Node.js 18+, Docker, Docker Compose, PostgreSQL 14+, Redis, Git

**Pasos:**

```bash
git clone https://github.com/DiegooLPZ-FTp/TeamTask-.git
cd TeamTask-

# Frontend
cd frontend && npm install
cd ../backend && npm install
```

Configurar variables de entorno:

**Backend** - `.env`:
```
DATABASE_URL=postgresql://user:password@localhost:5432/teamtask
REDIS_URL=redis://localhost:6379
JWT_SECRET=tu_secret_aqui
NODE_ENV=development
PORT=3000
```

**Frontend** - `.env`:
```
VITE_API_URL=http://localhost:3000
VITE_SOCKET_URL=http://localhost:3000
```

Ejecutar:
```bash
docker-compose up -d
cd backend && npx prisma migrate deploy

# Terminal 1
cd backend && npm run dev

# Terminal 2
cd frontend && npm run dev
```

Acceso: `http://localhost:5173`

---

## Uso

1. Crear equipo: Registrarse, acceder a "Mis Equipos", crear nuevo equipo, agregar miembros
2. Asignar tareas: Crear tarea, el sistema sugiere miembros según skills, disponibilidad y carga actual
3. Monitorear: Dashboard con estado general, carga de trabajo por persona, reportes exportables

---

## Estructura del Proyecto

```
TeamTask-/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── store/
│   │   ├── services/
│   │   └── styles/
│   └── vite.config.ts
│
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── models/
│   │   ├── middleware/
│   │   └── services/
│   ├── prisma/
│   └── .env.example
│
├── docker-compose.yml
└── .github/workflows/
```

---

## Equipo

Diego Alberto López Montes, Álvaro Gael García Ramírez, Christopher Mauricio Cuevas Medina, José Alexander de la Rosa

**Universidad:** Universidad Autónoma de Aguascalientes  
**Curso:** Análisis y Diseño de Sistemas (Grupo 5-B)  
**Profesor:** Erwin Brian Montes Chaparro

---

## Seguridad

Contraseñas encriptadas con bcrypt. Autenticación JWT stateless. CORS configurado. Headers de seguridad con Helmet. Rate limiting. Auditoría completa de acciones. Validación automática de datos.

---

## Testing

```bash
npm run test
npm run test:coverage
npm run test:watch
```

---

## Contribuciones

Fork el proyecto. Crear rama para feature. Commit cambios. Push. Abrir Pull Request.

---

## Licencia

MIT

---

## Soporte

Crear issue en: https://github.com/DiegooLPZ-FTp/TeamTask-/issues

