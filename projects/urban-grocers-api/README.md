# Proyecto: Urban Grocers (API REST)

**Tipo de proyecto:** Pruebas de API REST  
**Bootcamp:** TripleTen QA Manual + API  
**Objetivo:** Validar funcionalidad, respuestas, códigos de estado, esquemas y manejo de errores en endpoints clave de una API de supermercado online.

## Alcance de las pruebas
- Pruebas positivas y negativas  
- Validación de códigos HTTP (200, 201, 400, 401, 404, etc.)  
- Verificación de esquemas JSON (estructura de respuesta)  
- Manejo de casos límite (campos vacíos, valores inválidos, longitud máxima/mínima)  
- Autenticación básica (tokens, headers)  
- Pruebas de idempotencia en métodos PUT/DELETE cuando aplica

## Herramientas utilizadas
- **Postman** (colecciones y entornos)  
- Newman (opcional para ejecución automatizada en CI)  
- Jira para reporte de bugs (si se encontraron defectos)

## Endpoints probados (principales)
| Método | Endpoint                          | Descripción                              | Códigos esperados principales |
|--------|-----------------------------------|------------------------------------------|-------------------------------|
| POST   | /api/users/create                 | Crear usuario nuevo                      | 201, 400                      |
| GET    | /api/products                     | Listar productos disponibles             | 200, 401                      |
| POST   | /api/cart/add                     | Agregar producto al carrito              | 201, 400                      |
| DELETE | /api/cart/item/{id}               | Eliminar ítem del carrito                | 204, 404                      |
| PUT    | /api/users/update                 | Actualizar datos de usuario              | 200, 400                      |

## Resultados destacados
- **Total de requests ejecutados:** +80–100  
- **Endpoints con 100% cobertura positiva:** Listado de productos, creación de usuario válido  
- **Defectos encontrados:**  
  - Respuestas inconsistentes en errores 400 (algunos devuelven mensajes claros, otros genéricos)  
  - Falta de validación en longitud máxima de campos (ej: nombre de usuario muy largo)  
  - 401 no siempre incluye WWW-Authenticate header correcto

## Evidencias
- Colección Postman exportada: [urban-grocers-collection.json](urban-grocers-collection.json) (descárgala y ábrela en Postman)  
- Capturas de requests/responses exitosos y fallidos  
- Ejemplos de validaciones de esquema

## Reflexión del tester
Este proyecto me permitió practicar el uso avanzado de Postman (variables, tests automáticos con scripts, chain requests), entender la importancia de la documentación de API (Swagger/OpenAPI) y aprender a reportar bugs de API de forma clara y reproducible (pasos: método, URL, headers, body, respuesta esperada vs real).

¡Es uno de mis proyectos favoritos porque muestra habilidades técnicas más "dev-oriented"!
