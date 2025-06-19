# Introducción 🌐

Bienvenido a la documentación oficial de la API RESTful especializada en **alta relojería de lujo**. Esta API permite el acceso a catálogos detallados y datos históricos de algunas de las marcas más exclusivas del mundo.

## 🔍 ¿Qué ofrece esta API?

- Acceso a catálogos de relojes de:
  - **Patek Philippe**
  - **Rolex**
  - **Audemars Piguet**
- Histórico de precios en subastas
- Disponibilidad y ubicación de boutiques oficiales

---

## 🧭 Arquitectura de acceso

| Paso | Componente         | Descripción                                      |
|------|---------------------|--------------------------------------------------|
| 1    | Cliente             | El usuario o sistema que realiza las solicitudes. |
| 2    | Autenticación       | Verificación mediante token para asegurar el acceso. |
| 3    | Endpoints REST      | Puntos de entrada a los datos disponibles.        |
| 4    | Modelos de Relojes  | Información detallada sobre cada reloj.          |
| 5    | Colecciones         | Agrupaciones de relojes por marca o edición.     |
| 6    | Boutiques Oficiales | Datos de disponibilidad y ubicación física.      |
