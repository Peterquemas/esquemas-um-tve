# Esquemas UM TVE — Estado del proyecto

## Qué es
App HTML standalone para crear esquemas de sonido de unidades móviles de TV.
Sin servidor, sin dependencias. Un solo archivo.

## Archivos
- `esquemas-um.html` — la app completa
- `index.html` — copia idéntica para GitHub Pages (se sincroniza sola vía hook)
- `templates/` — 11 SVGs de iconos (camion_um, paneles, micros, IEM, etc.)
- `.git/hooks/pre-commit` — copia automática esquemas-um.html → index.html al hacer commit

## URLs
- Local: abrir `esquemas-um.html` directamente en el navegador
- Público: https://peterquemas.github.io/esquemas-um-tve/
- Repo: https://github.com/Peterquemas/esquemas-um-tve

## Flujo de trabajo
```bash
# Solo editar esquemas-um.html, el hook sincroniza index.html solo
git add esquemas-um.html
git commit -m "mensaje"
git push
```

## Estado actual (mayo 2026)
- App funciona: canvas SVG, 11 elementos arrastrables, conexiones, propiedades
- Exportar PDF: usa window.print() con @media print A3 landscape
  - Problema pendiente: a veces genera 2 páginas en lugar de 1
  - Workaround: en el diálogo del navegador → Escala: Ajustar al área imprimible
- Generar con Claude: requiere ANTHROPIC_API_KEY en ajustes (⚙ arriba derecha)
- La key se guarda en localStorage del navegador

## Pendiente / ideas
- Afinar el CSS de impresión para 1 página fiable
- Probar exportación SVG nativa
- Añadir más elementos al panel si hace falta
