# ESTADO — Estells (variante appli-style)

> Última actualización: 2026-07-01

## Qué es
Landing de **Estells Centre d'Estudis** (academia en Alginet, València) en **una sola página**, inspirada en la estética edtech de appli.global pero con diseño e identidad propios de Estells. No es clon: layout/estética adaptados, contenido/marca/imágenes de Estells.

## Stack / arquitectura
- **HTML + CSS + JS puro**, un único `index.html` autocontenido (sin build, sin frameworks, sin dependencias).
- Fuentes Google: Space Grotesk (titulares) + Inter (cuerpo).
- Assets en `images/` (logo, team/, strip/). Imágenes optimizadas (sips, ~80–320 KB).

## Online
- **Producción (alias):** https://estells.vercel.app
- **GitHub:** https://github.com/brenosiqn8n/estells-appli (público)
- **Vercel:** proyecto `estells-appli`, scope `brenon8n-7860s-projects`. Deploy manual con `vercel --prod` + `vercel alias set <deploy> estells.vercel.app`. **NO** hay auto-deploy desde GitHub conectado (se despliega a mano).

## Secciones (orden)
Nav (2 bloques: logo + menú) → Hero → Cómo funciona (proceso 3 pasos) → Sobre Estells (`#centro`, con dirección) → Por qué Estells (bento) → Equipo (`#equipo`) → Reseñas Google (`#resenas`, carrusel) → Contacto/Reserva (`#contacto`, formulario) → Footer. Badge flotante "Abierto ahora" abajo-izquierda.

## Funcionalidades hechas
- **Bilingüe ES / Valencià**: selector ES/VA en nav + menú móvil, motor i18n propio (`data-i18n`/`data-i18n-html`/`data-i18n-ph` + diccionario), persistencia `localStorage`, `<html lang>` dinámico. Reseñas quedan en su idioma original.
- **Nav**: dos bloques frosted-glass (logo grande + menú); al scrollear convergen animando el ancho (suave). Desactivado el efecto <1200px.
- **Hero**: título con palabra resaltada, fondo con blobs dorados a la deriva + retícula de puntos, pill "Curso 2026–2027" (año en negrita) con punto pulsante, 2 CTAs, rating Google.
- **Motion "tetris"**: bloques entran desde distintas direcciones (r-left/right/up/down) al scrollear; IntersectionObserver con **zona muerta** (0–0.2) para no vibrar; se re-animan en ambos sentidos. Respeta `prefers-reduced-motion`.
- **Bento** side-by-side (grupos, seguimiento, idiomas, horario, exámenes PAU).
- **Equipo**: tarjetas con imagen a tamaño completo (aspect 1/1), nombre+cargo sobreimpreso; Francesc marcado como **Director** (borde dorado + badge).
- **Reseñas**: carrusel auto-rotativo (6s) + flechas + dots, marca Google, avatar inicial. Datos en `REVIEWS` (JS) — **10 placeholder demo**, faltan las reales.
- **Formulario doble**: toggle Reserva/Contacta con fade-swap; validación nativa + **mailto** a estellscentre@gmail.com; WhatsApp + Instagram. Pitch izquierdo sticky (no se mueve al cambiar), título con degradado animado.
- **Badge "Abierto ahora"**: calcula L–V 16:00–20:30 Europe/Madrid, punto verde pulsante, bilingüe, actualiza cada minuto.
- **Botones sociales**: WhatsApp (verde) e Instagram (gradiente marca) se rellenan al hover.
- **Paleta**: adaptada al **amarillo del logo** (`--accent #F4C20D`, amber legible para texto, ink `#1a1a1a`).
- **Dirección real**: C/ Pérez Galdós 10, Alginet — en Sobre Estells + footer, enlazando a la **ficha real de Google Maps**.
- **SEO**: title/description/keywords locales, OG + Twitter, canonical, **JSON-LD EducationalOrganization** (dirección, geo 39.2661816/-0.4718064, tel, email, horario, Instagram, areaServed). Copy pasado por humanizer (menos tono folleto).
- **Responsive**: media queries 900px y 640px (nav CTA oculto en móvil, formulario 1 col, equipo 2 col, botones full-width, cards de reseñas con alto adaptativo).

## Pendientes / TODO
- **Datos reales**: teléfono (placeholder `+34 600 000 000`), reseñas reales de Google (sustituir `REVIEWS` en el JS), confirmar horario del badge (`// TODO` en `updateOpen`).
- **Reseñas Google automáticas**: ahora manual; se decidió dejarlo así. Opciones futuras: widget (Featurable) o API+serverless.
- **SEO extra**: falta `sitemap.xml` + `robots.txt`; dominio propio (mejor que vercel.app); alta en Google Business Profile.
- **Multipágina**: se planteó partir la landing en páginas (Inicio/Centro/Equipo/Reseñas/Contacto) — de momento **descartado**, sigue como landing única.
- **Auto-deploy**: conectar el repo de GitHub a Vercel para que cada push despliegue solo (ahora es manual con token).
- **Seguridad**: revocar el token de Vercel usado en sesión (se pegó en el chat).

## Relación con `estells/`
`../estells/` es la **versión React (Vite+Tailwind)** original de Estells (otra línea de diseño, con shader dorado). Esta carpeta `estells-appli/` es la variante estática estilo appli. Son proyectos separados.
