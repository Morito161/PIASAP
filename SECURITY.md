# Seguridad del prototipo PIASAP

PIASAP se publica como una demostración estática en GitHub Pages. **No proporciona autenticación real ni ejecuta auditorías de seguridad sobre objetivos.** La pantalla de acceso es exclusivamente visual. No deben introducirse credenciales reales, tokens, datos personales, secretos ni evidencias confidenciales.

## Controles incorporados
- Los metadatos de auditorías y campos de hallazgos que se insertan mediante plantillas HTML se escapan antes de representarse.
- La vista previa PDF se abre con `noopener,noreferrer` para impedir acceso a la pestaña de origen.
- Los informes y las evidencias actuales son simulados.

## Riesgos pendientes para una versión productiva
- Sustituir la autenticación visual por autenticación y autorización verificadas en un backend; **no** almacenar contraseñas ni secretos en JavaScript del navegador.
- Aplicar validación de entradas y autorización por recurso en el servidor.
- Evitar HTML construido dinámicamente con datos no confiables; preferir `textContent` y creación de nodos.
- Fijar las dependencias externas y utilizar Subresource Integrity (SRI) cuando corresponda. La biblioteca jsPDF se carga actualmente desde un CDN externo.
- Implementar una política Content Security Policy (CSP) compatible con una migración fuera de scripts y manejadores de eventos en línea.
- Guardar reportes y evidencias sensibles en almacenamiento privado con control de acceso, retención y registro de auditoría; nunca publicarlos en GitHub Pages.

**Importante:** estas mitigaciones son defensa en profundidad para una demo; no equivalen a una auditoría de penetración completa ni certifican ausencia de vulnerabilidades.
