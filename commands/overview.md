---
description: Resumen de la analítica web de un sitio en Anonymetrics (visitantes, páginas, fuentes)
argument-hint: [dominio o site id] [días]
---

Da un resumen claro de la analítica de un sitio medido con **Anonymetrics**.

Pasos:

1. Determina el sitio. Si el usuario no lo indicó en `$1`, llama a la tool
   `list_sites` (servidor MCP `anonymetrics`) y muéstrale la lista para que elija.
   Si `$1` es un dominio, resuélvelo contra `list_sites` para obtener su `site` id.
2. Con el `site` id, llama en paralelo a:
   - `get_stats` con `site` y `days` (usa `$2` si viene, si no 14).
   - `get_breakdown` con `site`, `dimension: "referrer"`, `limit: 5`.
   - `get_breakdown` con `site`, `dimension: "page"`, `limit: 5`.
3. Presenta un resumen en tablas: **visitantes, páginas vistas, eventos y vistas por
   visitante**; luego **top fuentes** y **top páginas**. Sé conciso y no inventes cifras.

Si el servidor MCP `anonymetrics` no está conectado o devuelve un error de
autorización, dilo con claridad y ofrece dos caminos:
- Conectar el conector remoto **https://mcp.anonymetrics.io** (autorizarás con tu
  API key de Anonymetrics), o
- Que el usuario pegue aquí las cifras de su panel y las organizas tú.
