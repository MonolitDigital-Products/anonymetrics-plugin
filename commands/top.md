---
description: Top valores de una dimensión (páginas, fuentes, países, navegadores…) en Anonymetrics
argument-hint: [dominio o site id] [dimensión] [días]
---

Lista los **valores principales de una dimensión** de un sitio de Anonymetrics.

Pasos:

1. Resuelve el sitio con `list_sites` (MCP `anonymetrics`) si `$1` no es un `site` id.
2. Interpreta la dimensión de `$2` y mapéala a una de las admitidas por `get_breakdown`:
   `page`, `referrer`, `country`, `city`, `browser`, `os`, `device`, `language`,
   `event`, `utm_source`, `utm_medium`, `utm_campaign`. Si no se indica, usa `page`.
3. Llama a `get_breakdown` con `site`, `dimension`, `days` (`$3` o 14) y `limit: 10`.
4. Presenta una tabla ordenada (etiqueta, visitantes, páginas vistas).

Para una serie temporal en lugar de un ranking, usa `get_timeseries`. Si el MCP
`anonymetrics` no está conectado, indícalo y sugiere el conector
**https://mcp.anonymetrics.io**.
