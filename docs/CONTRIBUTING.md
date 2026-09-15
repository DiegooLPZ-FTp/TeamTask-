# 🤝 Guía de Contribución - Team Task

¡Gracias por tu interés en contribuir a Team Task! Este documento te guiará a través del proceso.

---

## 📋 Tabla de Contenidos

1. [Código de Conducta](#código-de-conducta)
2. [Cómo Empezar](#cómo-empezar)
3. [Flujo de Trabajo](#flujo-de-trabajo)
4. [Convenciones de Código](#convenciones-de-código)
5. [Convenciones de Commits](#convenciones-de-commits)
6. [Pull Requests](#pull-requests)
7. [Testing](#testing)
8. [Documentación](#documentación)

---

## 🎯 Código de Conducta

Todos los contribuidores deben seguir nuestro código de conducta. Sé respetuoso, inclusivo y profesional en todas las interacciones.

---

## 🚀 Cómo Empezar

### 1. Fork del Repositorio

```bash
# Haz fork en GitHub
# Luego clona tu fork
git clone https://github.com/TU_USERNAME/TeamTask-.git
cd TeamTask-
```

### 2. Configurar Remoto Upstream

```bash
git remote add upstream https://github.com/DiegooLPZ-FTp/TeamTask-.git
git fetch upstream
```

### 3. Instalar Dependencias

```bash
npm run setup
```

### 4. Verificar que Todo Funciona

```bash
npm run test
```

---

## 🔄 Flujo de Trabajo

### 1. Crear Rama de Feature

```bash
# Actualiza develop
git checkout develop
git pull upstream develop

# Crea tu rama
git checkout -b feature/nombre-descriptivo
# o
git checkout -b bugfix/nombre-descriptivo
git checkout -b refactor/nombre-descriptivo
```

### 2. Desarrollar

```bash
# Realiza tus cambios
# Asegúrate de seguir las convenciones

# Ejecuta tests localmente
npm run test
npm run lint
npm run type-check
```

### 3. Commit

```bash
# Usa mensajes descriptivos (ver sección abajo)
git commit -m "feat(auth): Add user registration endpoint"
```

### 4. Push

```bash
git push origin feature/nombre-descriptivo
```

### 5. Pull Request

1. Ve a https://github.com/DiegooLPZ-FTp/TeamTask-
2. Click en "New Pull Request"
3. Compara tu rama con `develop`
4. Llena el template de PR
5. Request review de team members

---

## 📝 Convenciones de Código

### JavaScript/TypeScript

```typescript
// ✅ BIEN
interface User {
  id: string;
  email: string;
  createdAt: Date;
}

const getUserById = async (id: string): Promise<User> => {
  // Implementación
};

// ❌ MAL
interface user {
  id: any,
  email: any,
  createdAt: any
}

const getuserbyid = (id) => {
  // Implementación sin tipos
};
```

### Nombrado de Variables/Funciones

- **Funciones:** camelCase, verbo + sustantivo
  - ✅ `getUserById`, `calculateWorkload`
  - ❌ `get`, `func1`

- **Constantes:** UPPER_SNAKE_CASE
  - ✅ `MAX_FILE_SIZE`, `DEFAULT_PAGE_SIZE`
  - ❌ `max_file_size`, `defaultPageSize`

- **Interfaces/Types:** PascalCase
  - ✅ `User`, `TaskStatus`
  - ❌ `user`, `taskStatus`

### Estilos

```bash
# Ejecuta prettier y eslint antes de commit
npm run lint -- --fix
npm run type-check
```

---

## 💬 Convenciones de Commits

Usamos [Conventional Commits](https://www.conventionalcommits.org/)

### Formato

```
type(scope): subject

body

footer
```

### Tipos

- **feat:** Nueva característica
- **fix:** Arreglo de bug
- **docs:** Cambios en documentación
- **style:** Cambios de formato/estilos (no funcionales)
- **refactor:** Refactorización de código
- **test:** Añadir o actualizar tests
- **chore:** Tareas generales, dependencias

### Ejemplos

```bash
# Nueva característica
git commit -m "feat(tasks): Add intelligent assignment algorithm"

# Arreglo de bug
git commit -m "fix(auth): Resolve JWT token expiration issue"

# Documentación
git commit -m "docs(readme): Update setup instructions"

# Refactoring
git commit -m "refactor(api): Extract database queries to service layer"

# Tests
git commit -m "test(auth): Add login endpoint tests"

# Dependencias
git commit -m "chore(deps): Update React to 18.2.0"
```

---

## 🔄 Pull Requests

### Checklist Antes de Hacer PR

- [ ] Tests pasan localmente (`npm run test`)
- [ ] Linter sin errores (`npm run lint`)
- [ ] Type-check correcto (`npm run type-check`)
- [ ] Código está documentado
- [ ] No hay código comentado innecesario
- [ ] Branch está actualizado con `develop`

### Descripción del PR

```markdown
## 📋 Descripción
Breve descripción de qué hace este PR

## 🎯 Tipo de Cambio
- [x] Bug fix
- [ ] Nueva característica
- [ ] Breaking change

## 🔗 Issues Relacionados
Cierra #123

## ✅ Testing
- Describe cómo probaste
- Casos de borde considerados

## 📸 Screenshots (si aplica)
```

---

## 🧪 Testing

### Estructura de Tests

```typescript
// tests/services/auth.test.ts

import { describe, it, expect, beforeEach } from 'vitest';
import { registerUser } from '../services/auth';

describe('Auth Service', () => {
  describe('registerUser', () => {
    it('should register a new user with valid credentials', async () => {
      const result = await registerUser('test@example.com', 'password123');
      expect(result).toBeDefined();
      expect(result.email).toBe('test@example.com');
    });

    it('should throw error for duplicate email', async () => {
      // Test implementation
    });
  });
});
```

### Ejecutar Tests

```bash
# Tests en watch mode
npm run test -- --watch

# Tests con coverage
npm run test -- --coverage

# Tests específico
npm run test -- auth.test.ts
```

---

## 📚 Documentación

### Comentarios en Código

```typescript
/**
 * Calcula la carga de trabajo para un usuario
 * @param userId - ID del usuario
 * @param startDate - Fecha inicial
 * @param endDate - Fecha final
 * @returns Porcentaje de carga (0-100)
 */
export const calculateUserWorkload = (
  userId: string,
  startDate: Date,
  endDate: Date
): number => {
  // Implementación
};
```

### Archivos README

Cada carpeta importante debe tener su propio README:

```
backend/README.md
frontend/README.md
docs/API.md
docs/ARCHITECTURE.md
```

---

## 📞 Comunicación

- **Issues:** Para bugs, features, preguntas
- **Discussions:** Para ideas y debates
- **PR Review:** Feedback constructivo
- **Commits descriptivos:** Para entender la historia del código

---

## ✨ Tips para Contribuciones Exitosas

1. **Commits pequeños:** Cambios lógicos en commits separados
2. **Branch por feature:** Una rama por característica/bug
3. **Tests primero:** Escribe tests junto con el código
4. **Documentación:** Actualiza docs mientras codeas
5. **Revisa tu código:** Lee tu PR antes de hacer push
6. **Comunica:** Si hay dudas, pregunta antes de hacer cambios grandes

---

## 🙏 Gracias por Contribuir

Tu contribución es valorada y ayuda a hacer Team Task mejor. ¡Gracias por ser parte del proyecto! 🚀

---

Para más información, revisa:
- [README.md](../README.md)
- [GitHub Issues](https://github.com/DiegooLPZ-FTp/TeamTask-/issues)
- [Project Board](https://github.com/DiegooLPZ-FTp/TeamTask-/projects)
