# ProyectoFinalNorbertoMatadamas

# Proyecto E-commerce con Node.js, Express, MongoDB y WebSockets

Este proyecto es una aplicación de e-commerce desarrollada con Node.js, Express y MongoDB, que permite la gestión de productos y carritos de compra. Incluye funcionalidades de tiempo real utilizando WebSockets y vistas dinámicas con Handlebars.

## Características

- **Gestión de Productos**: CRUD completo para productos.
- **Gestión de Carritos**: CRUD completo para carritos de compra.
- **Persistencia de Datos**: MongoDB como base de datos principal.
- **Paginación y Filtros**: Consultas de productos con paginación, filtros y ordenamientos.
- **Vistas Dinámicas**: Handlebars como motor de plantillas.
- **Actualización en Tiempo Real**: WebSockets para la actualización de productos en tiempo real.

## Requisitos

- Node.js
- MongoDB

## Endpoints de la API

### Productos

- **GET /api/products**: Listar todos los productos con paginación, filtros y ordenamiento.
  - Query Params:
    - `limit`: Número de productos a devolver. Por defecto, 10.
    - `page`: Página a buscar. Por defecto, 1.
    - `query`: Filtro a aplicar (por categoría o disponibilidad).
    - `sort`: Ordenamiento por precio (`asc` o `desc`).

- **GET /api/products/:pid**: Obtener un producto por ID.

- **POST /api/products**: Crear un nuevo producto.
  - Campos requeridos: `title`, `description`, `code`, `price`, `stock`, `category`, `thumbnails`.

- **PUT /api/products/:pid**: Actualizar un producto por ID.

- **DELETE /api/products/:pid**: Eliminar un producto por ID.

### Carritos

- **POST /api/carts**: Crear un nuevo carrito.

- **GET /api/carts/:cid**: Listar productos de un carrito por ID.

- **POST /api/carts/:cid/product/:pid**: Agregar un producto al carrito por ID.

- **DELETE /api/carts/:cid/products/:pid**: Eliminar un producto del carrito por ID.

- **PUT /api/carts/:cid/products/:pid**: Actualizar la cantidad de un producto en el carrito por ID.

- **DELETE /api/carts/:cid**: Eliminar todos los productos de un carrito por ID.

## Vistas

- **GET /products**: Vista de todos los productos.
- **GET /realtimeproducts**: Vista de productos en tiempo real.
