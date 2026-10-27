# Senderos Güembé — sitio web

Sitio del operador de turismo **Senderos Güembé** (tours en el Biocentro Güembé, Urubó, Santa Cruz, Bolivia), desarrollado en la materia
Diseño Web I (SIS-0140) de la UPDS.

> **Proyecto académico.** Senderos Güembé es un operador ficticio creado para el curso: los precios, teléfonos, correo,
> personas y cifras del sitio son de ejemplo. No es el sitio oficial del Biocentro Güembé.

- **Sitio publicado:** https://sahoneropenaalanrdorigo-web.github.io/senderos-guembe/
- **Usuario de GitHub:** [sahoneropenaalanrdorigo-web](https://github.com/sahoneropenaalanrdorigo-web)
- **Tecnologías:** HTML5 semántico, CSS propio (variables, Flexbox, Grid, mobile-first, modo oscuro) y una versión
  alternativa de la portada con Bootstrap 5.3.8 (`version-bootstrap/`).
- **Calidad:** ver `INFORME_CALIDAD.md` (Lighthouse móvil en claro y oscuro, WCAG 2.2 AA, validación W3C, SEO técnico).

## Estructura
| Carpeta / archivo | Contenido |
|---|---|
| `index.html`, `tours.html`, `galeria.html`, `nosotros.html`, `contacto.html` | Páginas públicas |
| `legal/politicas.html`, `gracias.html`, `404.html` | Páginas de apoyo |
| `css/estilos.css` | Hoja de estilos del sitio |
| `img/`, `video/` | Imágenes optimizadas (WebP) y video con subtítulos |
| `version-bootstrap/` | Prototipo de la portada con Bootstrap |
| `robots.txt`, `sitemap.xml` | SEO técnico |
| `practica-auditoria.html` | Página de práctica del laboratorio 13, ya corregida (no se enlaza ni se indexa) |

## Documentos por laboratorio
| Laboratorio | Documento |
|---|---|
| 12 · Del wireframe a la página | `WIREFRAMES.md` (mapa del sitio y wireframes de "Nosotros") |
| 13 · Calidad medida | `INFORME_CALIDAD.md` |
| 14 · Publicación | este `README.md`, `.gitignore`, `.gitattributes`, `.nojekyll` |
| 15 · Arranque del proyecto | `BRIEF.md`, `PLAN.md` y los wireframes de la portada en `WIREFRAMES.md` |

## Decisiones
- **CSS propio y no Bootstrap:** en la comparación del laboratorio 11 la portada con CSS propio pesó unas 14 veces
  menos en código, y el público entra sobre todo desde el celular. La versión Bootstrap queda como prototipo.
- **Paleta "Laguna":** turquesa de las lagunas del Biocentro y naranja del pico del tucán, con contraste AA en claro y
  oscuro (detalle en los comentarios de `css/estilos.css`).
- **GitHub Pages:** gratis, publica con cada `git push` y permite un dominio propio más adelante.

## Cómo verlo en tu computadora
Abre la carpeta en VS Code y usa Live Server sobre `index.html`.

## Créditos
Contenido: caso del curso adaptado al Biocentro Güembé. Fotos: Wikimedia Commons, con licencias CC BY-SA (autores en `img/CREDITOS.md`).
Desarrollo: Alan Rodrigo Sahonero Peña — Diseño Web I, UPDS, 2026.
