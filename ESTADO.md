# ESTADO — Estells (variante estilo appli.global)

> Última actualización: 2026-06-28

## Qué es
Variante experimental ("prueba") de la web de Estells inspirada en la **estética y estructura de appli.global** (edtech app-style): sans bold, blanco, acento esmeralda, mucho aire, hero centrado con keyword resaltada, proceso 3 pasos, features grid, stats, split misión, equipo, banda CTA, footer.

**No clona** appli 1:1: layout/estética adaptados; textos, marca, imágenes y datos son de Estells (IP respetada).

## Stack
- **HTML + CSS + JS puro**, un solo archivo `index.html` (autocontenido, sin build ni deps).
- Fuentes: Space Grotesk (titulares) + Inter (cuerpo) vía Google Fonts.
- Motion: scroll reveal (IntersectionObserver), marquee CSS, nav scroll-state, menú móvil. Respeta `prefers-reduced-motion`.

## Independiente
Carpeta hermana de `estells/` (proyecto React). **No comparte** código ni repo; la web original no se ha tocado. Assets copiados en `images/` (logo, team, strip).

## Cómo verla
Abrir `index.html` en el navegador (doble clic) o `python3 -m http.server` dentro de la carpeta.

## Pendientes (si se elige esta vía)
- [ ] Confirmar paleta real de appli (el fetch no dio hex; acento esmeralda elegido por aproximación edtech).
- [ ] Datos reales (teléfono, Instagram, reseñas Google) — ahora placeholders.
- [ ] Decidir bilingüe ES/VA si se continúa.
- [ ] Versión final: portar a React/Astro o dejar estático.
