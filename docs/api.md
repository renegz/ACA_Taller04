# API Reference

Esta sección documenta todos los endpoints disponibles en la API de Bananabook.

!!! note "Base URL"
    Todas las rutas están prefijadas con `https://api.bananabook.com/v1`

## Autenticación

La API utiliza JWT (JSON Web Tokens) para la autenticación. Incluye el token en el header `Authorization`:

=== "JavaScript"
    ```javascript
    const headers = {
      'Authorization': `Bearer ${token}`,
      'Content-Type': 'application/json'
    };

    fetch('/api/posts', { headers })
      .then(response => response.json())
      .then(data => console.log(data));
    ```

=== "cURL"
    ```bash
    curl -H "Authorization: Bearer YOUR_TOKEN" \
         -H "Content-Type: application/json" \
         https://api.bananabook.com/v1/posts
    ```

## Endpoints

### Usuarios

| Método | Endpoint | Descripción | Autenticación |
|--------|----------|-------------|---------------|
| `POST` | `/auth/register` | Registrar nuevo usuario | No |
| `POST` | `/auth/login` | Iniciar sesión | No |
| `GET` | `/users/profile` | Obtener perfil del usuario | Sí |
| `PUT` | `/users/profile` | Actualizar perfil | Sí |
| `GET` | `/users/:id` | Obtener usuario por ID | Sí |

### Posts

| Método | Endpoint | Descripción | Autenticación |
|--------|----------|-------------|---------------|
| `GET` | `/posts` | Obtener feed de posts | Sí |
| `POST` | `/posts` | Crear nuevo post | Sí |
| `GET` | `/posts/:id` | Obtener post específico | Sí |
| `PUT` | `/posts/:id` | Actualizar post | Sí |
| `DELETE` | `/posts/:id` | Eliminar post | Sí |

## Códigos de Estado

| Código | Descripción |
|--------|-------------|
| `200` | Operación exitosa |
| `201` | Recurso creado exitosamente |
| `400` | Error en la solicitud |
| `401` | No autorizado |
| `403` | Prohibido |
| `404` | Recurso no encontrado |
| `500` | Error interno del servidor |

!!! danger "Límites de Rate"
    La API tiene un límite de 1000 requests por hora por usuario autenticado.

Para más información sobre la configuración inicial, visita la [guía de inicio](getting-started.md#instalacion).
