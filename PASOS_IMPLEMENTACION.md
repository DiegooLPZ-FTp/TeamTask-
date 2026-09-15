# 📋 GUÍA PASO A PASO: Implementar Estructura en GitHub

## 🎯 Objetivo
Convertir tu repositorio de documentación-only a un proyecto **profesional, organizado y listo para desarrollar**.

---

## ✅ PASO 1: Preparar Repositorio Local (5 min)

### 1.1 Si no tienes nada en local:

```bash
# Clona tu repositorio
git clone https://github.com/DiegooLPZ-FTp/TeamTask-.git
cd TeamTask-

# Verifica la rama actual
git branch
# Deberías estar en 'main' o 'master'
```

### 1.2 Si ya tienes archivos guardados:

```bash
# Asegúrate de tener los cambios actualizados
git status
git pull origin main
```

---

## ✅ PASO 2: Crear la Estructura de Carpetas (2 min)

```bash
# Desde la raíz del proyecto TeamTask-

# Carpetas principales
mkdir -p frontend/src/{components,pages,hooks,services,store,types,styles}
mkdir -p frontend/public
mkdir -p backend/src/{controllers,services,models,routes,middleware,utils,types,config}
mkdir -p backend/prisma/migrations
mkdir -p backend/tests
mkdir -p docs/diagrams
mkdir -p docker
mkdir -p .github/workflows
mkdir -p .github/ISSUE_TEMPLATE

# Verificar que se crearon
tree -L 2
# o
find . -type d | head -20
```

---

## ✅ PASO 3: Copiar Archivos de Configuración (5 min)

### Opción A: Descargar archivo ZIP y descomponer
Si tienes un ZIP con todos los archivos, extrae en la raíz del proyecto.

### Opción B: Copiar manualmente

1. **Archivos en raíz:**
   - `.gitignore` → Raíz del proyecto
   - `README.md` → Raíz
   - `LICENSE` → Raíz
   - `CHANGELOG.md` → Raíz

2. **Archivos en .github:**
   - `.github/PULL_REQUEST_TEMPLATE.md`
   - `.github/ISSUE_TEMPLATE/feature.md`
   - `.github/ISSUE_TEMPLATE/bug.md`
   - `.github/ISSUE_TEMPLATE/config.yml`
   - `.github/workflows/ci-backend.yml`
   - `.github/workflows/ci-frontend.yml`

3. **Archivos de configuración:**
   - `frontend/.env.example`
   - `backend/.env.example`

4. **Documentación:**
   - `docs/CONTRIBUTING.md`

---

## ✅ PASO 4: Añadir Archivos package.json Base (10 min)

### 4.1 Frontend - `frontend/package.json`

```json
{
  "name": "teamtask-frontend",
  "version": "0.1.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview",
    "test": "vitest",
    "type-check": "tsc --noEmit"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "axios": "^1.6.0",
    "socket.io-client": "^4.7.0",
    "zustand": "^4.4.0"
  },
  "devDependencies": {
    "@types/react": "^18.2.0",
    "@types/react-dom": "^18.2.0",
    "@vitejs/plugin-react": "^4.2.0",
    "vite": "^5.0.0",
    "typescript": "^5.2.0",
    "tailwindcss": "^3.3.0",
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.0",
    "eslint": "^8.54.0",
    "vitest": "^0.34.0"
  }
}
```

### 4.2 Backend - `backend/package.json`

```json
{
  "name": "teamtask-backend",
  "version": "0.1.0",
  "type": "module",
  "scripts": {
    "dev": "node --loader ts-node/esm src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js",
    "lint": "eslint src --ext ts",
    "test": "vitest",
    "type-check": "tsc --noEmit",
    "migrate": "prisma migrate dev",
    "generate": "prisma generate",
    "seed": "ts-node --esm prisma/seed.ts"
  },
  "dependencies": {
    "express": "^4.18.0",
    "cors": "^2.8.5",
    "helmet": "^7.0.0",
    "dotenv": "^16.3.0",
    "jsonwebtoken": "^9.1.0",
    "bcryptjs": "^2.4.0",
    "@prisma/client": "^5.0.0",
    "redis": "^4.6.0",
    "socket.io": "^4.7.0",
    "axios": "^1.6.0",
    "nodemailer": "^6.9.0"
  },
  "devDependencies": {
    "@types/express": "^4.17.0",
    "@types/node": "^20.0.0",
    "@types/cors": "^2.8.0",
    "@types/jsonwebtoken": "^9.0.0",
    "@types/bcryptjs": "^2.4.0",
    "typescript": "^5.2.0",
    "ts-node": "^10.9.0",
    "prisma": "^5.0.0",
    "eslint": "^8.54.0",
    "vitest": "^0.34.0"
  }
}
```

### 4.3 Raíz (Opcional) - `package.json`

```json
{
  "name": "teamtask",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "setup": "npm install && cd frontend && npm install && cd ../backend && npm install",
    "dev": "npm run dev --workspace=frontend & npm run dev --workspace=backend",
    "docker": "docker-compose up -d",
    "docker-down": "docker-compose down"
  },
  "workspaces": [
    "frontend",
    "backend"
  ]
}
```

---

## ✅ PASO 5: Configuración Inicial de Git (5 min)

```bash
# 1. Verificar status
git status

# 2. Agregar todos los archivos
git add .

# 3. Crear commit inicial
git commit -m "chore: Initialize project structure with frontend, backend, and documentation

- Create folder structure for React frontend and Node.js backend
- Add GitHub Actions CI/CD workflows
- Add issue and PR templates
- Add base configuration files (.gitignore, .env.example)
- Add README and contributing guidelines"

# 4. Push a main
git push origin main

# Si hay conflicto:
git pull origin main
# Resuelve conflictos y:
git add .
git commit -m "chore: Resolve merge conflicts"
git push origin main
```

---

## ✅ PASO 6: Crear Rama de Desarrollo (3 min)

```bash
# 1. Crear rama develop desde main
git checkout -b develop

# 2. Push de la nueva rama
git push -u origin develop

# 3. Configurar develop como rama base en GitHub (Settings → Branches)
```

---

## ✅ PASO 7: Proteger Ramas en GitHub (5 min)

### En GitHub.com:

1. Ir a **Settings** → **Branches**

2. Hacer clic en **Add Rule**

3. **Para rama `main`:**
   - Branch name pattern: `main`
   - ✅ Require a pull request before merging
   - ✅ Require status checks to pass before merging
   - ✅ Require reviews from code owners
   - ✅ Require approval of the most recent reviewers
   - ✅ Dismiss stale pull request approvals
   - ✅ Require conversation resolution before merging

4. **Para rama `develop`:**
   - Branch name pattern: `develop`
   - ✅ Require a pull request before merging
   - ✅ Require status checks to pass before merging
   - (Opcional: ✅ Require reviews)

---

## ✅ PASO 8: Habilitar GitHub Actions (2 min)

### En GitHub.com:

1. Ir a **Settings** → **Actions** → **General**
2. Seleccionar **Allow all actions and reusable workflows**
3. Hacer clic en **Save**

---

## ✅ PASO 9: Crear GitHub Project (5 min)

### Opción A: Project Board (Clásico)

1. Ir a **Projects** → **New Project**
2. Elegir template: **Kanban**
3. Crear columnas:
   - **Backlog** (issues nuevos)
   - **Ready** (tareas listas para comenzar)
   - **In Progress** (en desarrollo)
   - **Review** (pendiente de PR review)
   - **Done** (completadas)

### Opción B: Project Board (Beta - Recomendado)

1. Ir a **Projects** → **New Project**
2. Elegir **Table** view
3. Configurar campos personalizados:
   - Priority: High/Medium/Low
   - Status: Backlog/Ready/In Progress/Review/Done
   - Parcial: 1er/2do/3er/4to

---

## ✅ PASO 10: Crear Issues Iniciales (15 min)

### Issues por Requisito Funcional

Para cada RF (28 totales), crear un issue:

**Título:** `[RF-01] Registrar nuevo usuario`

**Template:**
```markdown
## Descripción
RF-01 del 1er Parcial

## Requisito Completo
Registrar nuevo usuario con email y contraseña

## Criterios de Aceptación
- [ ] Endpoint POST /api/auth/register
- [ ] Validación de email
- [ ] Hash de contraseña con bcryptjs
- [ ] Tests unitarios

## Asignado
2do Parcial - Backend
```

**Labels:** 
- `backend` o `frontend`
- `2do-parcial`
- `enhancement`

### Issues por Tarea de Infraestructura

- [ ] Setup inicial de Prisma y PostgreSQL
- [ ] Configurar Redis para sesiones
- [ ] Setup de Socket.io real-time
- [ ] Configurar autenticación JWT
- [ ] Setup de testing con Vitest
- [ ] Documentar API endpoints

---

## ✅ PASO 11: Configurar Equipo de Colaboradores (2 min)

### En GitHub.com:

1. Ir a **Settings** → **Collaborators** 
2. Invitar a team members:
   - Diego Alberto López Montes
   - Álvaro Gael García Ramírez
   - Christopher Mauricio Cuevas Medina
   - José Alexander de la Rosa

3. Asignar rol: **Maintain** (pueden hacer merge)

---

## ✅ PASO 12: Configurar Code Owners (Opcional, 2 min)

### Crear `.github/CODEOWNERS`

```
# Backend
backend/ @diego @alvaro

# Frontend
frontend/ @christopher @jose

# Documentación
docs/ @team

# GitHub configuration
.github/ @team
```

---

## 🎉 ¡Listo! Checklist Final

- [ ] Estructura de carpetas creada
- [ ] Archivos de configuración en lugar
- [ ] Rama `develop` creada
- [ ] Ramas protegidas (main y develop)
- [ ] GitHub Actions habilitado
- [ ] Project Board creado
- [ ] Issues iniciales creados
- [ ] Colaboradores invitados
- [ ] README actualizado

---

## 📝 Próximos Pasos

### En Local (Tu computadora):

```bash
# 1. Cambiar a rama develop
git checkout develop

# 2. Crear rama para feature del 2do Parcial
git checkout -b feature/auth-system

# 3. Crear estructura de carpetas del proyecto
cd frontend && npm init -y
cd ../backend && npm init -y

# 4. Instalar dependencias
npm run setup

# 5. Comenzar a desarrollar!
```

### En GitHub (Online):

1. Usar **Project Board** para organizar el trabajo
2. Crear **Issues** por cada tarea
3. Hacer **PRs** en lugar de commits directos a develop
4. Revisar código entre team members
5. Usar **Discussions** para preguntas

---

## 🆘 Troubleshooting

### Error: "Permission denied" al push

```bash
# Verificar que estés autenticado
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@example.com"

# Usar HTTPS o SSH según tu preferencia
git remote -v
```

### Error: "Branch is out of date"

```bash
# Actualizar tu rama con main/develop
git fetch origin
git rebase origin/develop
# o
git merge origin/develop
```

### Workflow CI falla

1. Verificar `.github/workflows/*.yml` está bien formado
2. Revisar output del workflow en GitHub → Actions
3. Asegurarse de que `package.json` existe en cada carpeta

---

## 📚 Referencias

- [GitHub Docs - Protecting Branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [GitHub Actions - Documentation](https://docs.github.com/en/actions)
- [Git Workflow - Feature Branches](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)

---

**¡Tu GitHub estará profesional y listo para desarrollar Team Task! 🚀**

Cualquier duda, abre un issue en el proyecto.
