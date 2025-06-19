# Primeros Pasos

Esta guía te ayudará a ejecutar Bananabook en tu entorno de desarrollo local.

!!! warning "Requisitos previos"
    Antes de comenzar, asegúrate de tener instalado Node.js v16+, npm/yarn y MongoDB.

## Estructura del Monorepo

El proyecto Bananabook está organizado como un monorepo con la siguiente estructura:

| Directorio | Descripción | Tecnología |
|------------|-------------|------------|
| `/frontend` | Aplicación cliente | React.js |
| `/backend` | API del servidor | Express.js |
| `/shared` | Código compartido | TypeScript |

## Comandos de Ejecución

### Instalación de Dependencias

=== "Raíz del proyecto"
    ```bash
    # Instalar todas las dependencias del monorepo
    npm install
    ```

=== "Por separado"
    ```bash
    # Backend
    cd backend && npm install
    
    # Frontend
    cd frontend && npm install
    ```

### Ejecutar la Aplicación

=== "Modo Desarrollo"
    ```bash
    # Ejecutar frontend y backend simultáneamente
    npm run dev
    
    # O ejecutar por separado:
    npm run dev:backend   # Puerto 5000
    npm run dev:frontend  # Puerto 3000
    ```

=== "Modo Producción"
    ```bash
    # Build y ejecutar
    npm run build
    npm start
    ```

## Variables de Entorno

Crea los siguientes archivos de configuración:

| Archivo | Ubicación | Variables requeridas |
|---------|-----------|---------------------|
| `.env` | `/backend/` | `MONGODB_URI`, `JWT_SECRET`, `PORT` |
| `.env.local` | `/frontend/` | `REACT_APP_API_URL` |

!!! tip "Configuración rápida"
    Puedes copiar los archivos `.env.example` incluidos en cada directorio.

## Comandos Útiles

```bash
# Limpiar node_modules y reinstalar
npm run clean && npm install

# Ejecutar tests
npm test

# Lint y formato de código
npm run lint
npm run format

# Build para producción
npm run build
```

## Verificar Instalación

Una vez ejecutados los comandos, verifica que todo funcione:

1. **Backend**: `http://localhost:5000/api/health`
2. **Frontend**: `http://localhost:3000`
3. **MongoDB**: Conexión establecida en los logs del backend

Para más información sobre los endpoints disponibles, consulta la [documentación de la API](api.md).

¡Ya tienes Bananabook ejecutándose localmente! 🍌
