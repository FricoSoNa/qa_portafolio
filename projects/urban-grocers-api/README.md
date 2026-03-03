# Proyecto: Urban Grocers (API REST)

**Tipo de proyecto:** Pruebas Manuales de API REST  
**Bootcamp:** TripleTen QA Manual + API - 4.º Sprint  
**Objetivo:** Validar endpoints de gestión de kits de productos y servicio de entrega "Order and Go", cubriendo casos positivos, negativos, valores límite y manejo de errores.

## Alcance de las pruebas
- 37 casos de prueba ejecutados  
- Pruebas positivas y negativas  
- Validación de códigos HTTP (200, 400, 404, 500)  
- Pruebas de valores límite y tipos de datos incorrectos  
- Validación de esquemas y mensajes de error

## Endpoints probados

### 1. Gestión de Kits (`/api/v1/kits/:id/products`)
- Agregar productos a un kit existente
- Validaciones de cantidad máxima (30 productos únicos)
- Manejo de productos inexistentes
- Validación de estructura del body (JSON)

### 2. Servicio de Entrega "Order and Go" (`/order-and-go/v1/delivery`)
- Cálculo de tiempo de entrega según `deliveryTime`, `productsCount` y `productsWeight`
- Rangos válidos e inválidos
- Costos adicionales (`hostDeliveryCost` y `clientDeliveryCost`)

## Resultados generales
- **Casos ejecutados:** 37  
- **Passed:** 24 (65%)  
- **Failed:** 13 (35%)  
- **Defectos reportados:** 13 (varios de severidad Alta/Media)

## Defectos más relevantes encontrados

| Bug ID       | Descripción                                              | Severidad | Endpoint                     | Código obtenido |
|--------------|----------------------------------------------------------|---------|------------------------------|-----------------|
| ProdEx_1     | Se agregan productos inexistentes y quantity se suma     | Alta    | POST /kits/:id/products      | 200 en vez de 400 |
| RespServ_1   | Quantity como string devuelve 500 en vez de 400          | Alta    | POST /kits/:id/products      | 500             |
| RespServ_2   | ID como string devuelve HTML de error 500                | Alta    | POST /kits/:id/products      | 500             |
| DelivTime_1  | deliveryTime = 7 (fuera de rango) aceptado               | Alta    | POST /order-and-go/v1/delivery | 200 en vez de 400 |
| DelivTime_3  | deliveryTime como string "uno" aceptado                  | Alta    | POST /order-and-go/v1/delivery | 200 en vez de 400 |
| ProdCount_1  | productsCount negativo aceptado                          | Media   | POST /order-and-go/v1/delivery | 200             |


## Reflexión del tester
Este proyecto fue clave para practicar **testing de API a profundidad**: validaciones de esquema, boundary testing (máximos y mínimos), manejo de errores y cómo reportar defectos de backend de forma clara y reproducible.

Aprendí mucho sobre la importancia de las validaciones en el lado del servidor y cómo un pequeño error en el body puede generar respuestas inesperadas (500 Internal Server Error).

O si prefieres, dime “siguiente” y te doy el siguiente archivo listo para copiar-pegar.

¡Ya casi tenemos Urban Grocers terminado y se ve muy profesional! 🔥
