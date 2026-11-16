# Reglas de trabajo — simulador-hipotecario

Sitio estático (HTML) publicado en Vercel desde la raíz del repo. Los archivos `CLAUDE.md` y `.claude/` están excluidos de la publicación en `.vercelignore`; no los quites.

## Idioma y estilo
- Responde siempre en español, con lenguaje simple y sin tecnicismos. Manuel no es programador.
- Viñetas cortas. Al final de cada entrega di qué cambió, qué probaste y qué no pudiste probar.

## Indicador de modelo (en cada respuesta)
- Empieza cada respuesta con el modelo que estás usando:
  - 🟢 **Opus 5.5**
  - 🔵 **Fable 5.2**
- Al presentar un plan, recomienda el modelo adecuado para esa tarea:
  - 🟢 Opus 5.5 (por defecto): cambios Chicos y Medianos.
  - 🔵 Fable 5.2: cambios Grandes y complejos (app o módulo nuevo, arquitectura, un problema que Opus no resolvió). Consume más límite de uso, así que solo cuando valga la pena.
- Si el modelo en uso no es el recomendado, avísalo y sugiere cambiar con `/model opus` o `/model fable`.

## Flujo según el tamaño del cambio
Antes de tocar cualquier archivo, clasifica la petición como **Chico**, **Mediano** o **Grande** y dilo al inicio del plan.

- **Chico** (un texto, un precio, un color, un ajuste menor):
  plan → aprobación de Manuel → publicar (commit y push a `main`).
- **Mediano** (sección nueva, rediseño de una pantalla, una función nueva sencilla):
  plan → aprobación → rama nueva + Pull Request → compartir el link de prueba de Vercel → aprobación → publicar (merge a `main`).
- **Grande** (app o módulo nuevo, cualquier cambio en Supabase, cambios en varias páginas):
  plan → mockup visual → aprobación → rama nueva + Pull Request → compartir el link de prueba de Vercel → aprobación → publicar (merge a `main`).

Si tienes duda entre dos tamaños, elige el más grande.

## Reglas que no se rompen
- No modifiques ningún archivo sin la aprobación explícita de Manuel ("aprobado", "va", "sí, hazlo").
- Publicar = llegar a `main`. Nunca publiques sin su aprobación del resultado final.
- Supabase es la base de datos real con datos de clientes:
  - Cualquier cambio a tablas, columnas, permisos (RLS) o datos cuenta como **Grande**.
  - Nunca borres tablas, columnas ni registros sin confirmación explícita, aunque el plan ya esté aprobado.
  - Nunca pongas la llave `service_role` en código que llegue al navegador.
- Respeta la paleta, tipografía y estilo actuales del sitio salvo que Manuel pida cambiarlos.
- Todo debe verse bien en celular.
- Pide permiso explícito antes de conectarte a la computadora de Manuel, cada vez.
