# Proyecto: Urban Routes (Web App)

**Tipo de proyecto:** Pruebas manuales de una aplicación web de transporte compartido  
**Bootcamp:** TripleTen QA Manual + API  
**Objetivo:** Validar funcionalidad, diseño, usabilidad y lógica crítica del flujo de reserva.

## Alcance de las pruebas
- Pruebas de **diseño y UI** (checklist visual)
- Pruebas del **formulario de reserva** y tarifas
- Pruebas de la ventana **"Método de pago"** y **"Agregar tarjeta"**
- Pruebas de la lógica del botón **"Reservar"**

## Herramientas utilizadas
- Navegadores: Chrome (800×600) y Firefox (1920×1080)
- Jira (reporte de bugs)
- Google Sheets (listas de comprobación)

## Resultados generales
- **Total de pruebas ejecutadas:** +60  
- **Aprobadas:** 80%+  
- **Defectos encontrados y reportados:** 12 (varios de severidad media)

## Defectos más relevantes encontrados
| ID Bug       | Descripción                                      | Severidad | Navegador     |
|--------------|--------------------------------------------------|---------|---------------|
| CasVer_1     | Checkbox "Luz de discoteca" no funciona         | Media   | Ambos         |
| TxtReq_1     | Radio button "Bebidas para pasajeros" falla     | Media   | Ambos         |
| TxtReq_2     | Radio button "Fruta para pasajeros" falla       | Media   | Ambos         |
| TxtReq_3     | Taxímetro "Copas frías" no responde             | Media   | Ambos         |
| NumTar_Esp_1 | Espacios en número de tarjeta no se agregan correctamente | Alta | Firefox     |
| NumCaract_1  | Se permite menos de 12 dígitos en tarjeta       | Alta    | Ambos         |
| ChromeError_1| Temporizador de espera gratuita no inicia correctamente | Media | Chrome      |

**Reflexión del tester:**  
Este proyecto me permitió practicar técnicas de clases de equivalencia y valores límite, además de identificar problemas reales de usabilidad que afectan directamente la experiencia del usuario.
