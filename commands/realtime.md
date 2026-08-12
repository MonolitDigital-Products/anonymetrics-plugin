---
description: Visitantes activos ahora mismo en un sitio de Anonymetrics
argument-hint: [dominio o site id]
---

Muestra los **visitantes activos en los últimos 5 minutos** en un sitio de Anonymetrics.

Pasos:

1. Resuelve el sitio: si `$1` no viene o es un dominio, usa `list_sites` (MCP
   `anonymetrics`) para obtener el `site` id correcto.
2. Llama a `get_realtime` con ese `site`.
3. Responde en una frase con el número de activos ahora. Si el usuario quiere más
   contexto, ofrécele `/overview` para el resumen del periodo.

Si el MCP `anonymetrics` no está conectado, indícalo y sugiere añadir el conector
**https://mcp.anonymetrics.io**.
