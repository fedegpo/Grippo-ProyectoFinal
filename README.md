# Grippo-ProyectoFinal
Gestor de ideas e inspiración visual hecho con ASP.NET Core MVC + Vue.js. Incluye login con roles, subida de imágenes, API JWT y CRUD con AJAX.

---

## Tecnologías

- **ASP.NET Core MVC**  
- **Entity Framework Core**  
- **PostgreSQL**  
- **Vue.js**  
- **TailwindCSS**  
- **JWT (JSON Web Tokens)** para autenticación de la API  
- **ASP.NET Identity** para gestión de usuarios y roles  

---

## Modelo de base de datos

### Entidades principales

| Entidad | Descripción |
|----------|-------------|
| **Usuario** | Representa al usuario registrado. Contiene su avatar, rol y credenciales. |
| **Inspiración** | Idea visual compartida (imagen, descripción, categoría). |
| **Categoría** | Agrupa las inspiraciones según temática. |
| **Colección** | Carpeta o tablero donde el usuario guarda sus inspiraciones favoritas. |
| **Comentario** | Opinión o feedback de usuarios sobre una inspiración. |

---

## Relaciones entre entidades

| Relación | Tipo | Descripción |
|-----------|------|-------------|
| Usuario → Inspiraciones | 1 a N | Un usuario puede subir muchas inspiraciones. |
| Usuario → Colecciones | 1 a N | Un usuario puede crear varias colecciones. |
| Usuario → Comentarios | 1 a N | Un usuario puede dejar varios comentarios. |
| Categoría → Inspiraciones | 1 a N | Cada inspiración pertenece a una categoría. |
| Colección ↔ Inspiración | N a N | Una inspiración puede estar en muchas colecciones. |
| Inspiración → Comentarios | 1 a N | Una inspiración puede tener varios comentarios. |

### Diagrama de entidades

Usuario 1---N Inspiraciones 1---N Comentarios
Usuario 1---N Colecciones N---N Inspiraciones
Categoría 1---N Inspiraciones

---

## Seguridad

El sistema usa **ASP.NET Identity** para manejar los usuarios y roles, y **JWT (JSON Web Tokens)** para proteger la API.

- Cada usuario tiene un **rol**: *Administrador* o *Usuario*.  
- El **Administrador** puede gestionar usuarios, categorías e inspiraciones.  
- El **Usuario** puede subir, editar y eliminar sus propias inspiraciones, crear colecciones y comentar.  
- Las secciones restringidas se controlan con `[Authorize]` y `[Authorize(Roles = "Admin")]`.  

---

## Funcionalidades principales

### Usuarios
- Registro e inicio de sesión.
- Avatares personalizados.
- Roles y permisos diferenciados.
- Perfil público con sus inspiraciones y colecciones.

### Inspiraciones
- Subida de imágenes con título y descripción.
- Filtros por categoría.
- Paginado dinámico en el listado.
- CRUD completo implementado con **Vue.js** y AJAX.

### Categorías
- Gestión por parte del administrador.
- Selección con búsqueda por AJAX al crear una inspiración.

### Colecciones
- Creación y edición de colecciones personales.
- Asociación de inspiraciones mediante relación N:N.

### Comentarios
- Los usuarios pueden comentar inspiraciones de otros.
- Sistema básico de moderación (el admin puede borrar).

---

## Autor

Federico Grippo
