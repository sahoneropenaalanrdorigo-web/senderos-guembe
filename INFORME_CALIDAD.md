# Informe de calidad — Senderos Güembé

Fecha de medición: 26 de octubre de 2026.

Herramientas: Lighthouse 12.8.2 (móvil, Microsoft Edge sin cabecera, sitio servido por HTTP en la ruta
`/senderos-guembe/`, igual que en GitHub Pages), html-validate 9.7.1 (reglas recomendadas + a11y), validador de CSS
del W3C (jigsaw), Playwright con Edge (anchos de 320 a 1280 px, teclado, preferencias de color y de movimiento) y
medición propia de contraste sobre capturas.

## 1. Lighthouse (móvil)
| Página | Tema | Rendimiento | Accesibilidad | Buenas prácticas | SEO | LCP | CLS | Peso |
|---|---|---|---|---|---|---|---|---|
| index (antes) | claro | 93 | 100 | 100 | 100 | 3,2 s | 0 | 434 KiB |
| index (antes) | oscuro | 93 | 100 | 100 | 100 | 3,2 s | 0 | 434 KiB |
| index (después) | claro | 97 | 100 | 100 | 100 | 2,6 s | 0 | 329 KiB |
| index (después) | oscuro | 97 | 100 | 100 | 100 | 2,6 s | 0 | 329 KiB |
| tours | claro | 100 | 100 | 100 | 100 | 1,0 s | 0 | 30 KiB |
| tours | oscuro | 100 | 100 | 100 | 100 | 0,9 s | 0 | 30 KiB |
| galeria | claro | 96 | 100 | 100 | 100 | 2,7 s | 0 | 465 KiB |
| galeria | oscuro | 96 | 100 | 100 | 100 | 2,7 s | 0 | 465 KiB |
| nosotros | claro | 100 | 100 | 100 | 100 | 0,9 s | 0 | 26 KiB |
| nosotros | oscuro | 100 | 100 | 100 | 100 | 0,9 s | 0 | 26 KiB |
| contacto | claro | 100 | 100 | 100 | 100 | 1,0 s | 0 | 490 KiB |
| contacto | oscuro | 100 | 100 | 100 | 100 | 1,0 s | 0 | 490 KiB |
| version-bootstrap | claro | 88 | 100 | 100 | 100 | 3,7 s | 0 | 543 KiB |
| practica-auditoria (corregida) | claro | 100 | 100 | 100 | 100 | 1,4 s | 0 | 92 KiB |
| practica-auditoria (corregida) | oscuro | 100 | 100 | 100 | 100 | 1,4 s | 0 | 92 KiB |

"Antes" y "después" de la portada corresponden a la corrección 2 de la tabla siguiente. Los valores de rendimiento
varían unos puntos entre ejecuciones; se reporta una ejecución por página y tema.

## 2. Hallazgos y correcciones
| # | Hallazgo (herramienta) | Criterio | Corrección | Verificación |
|---|---|---|---|---|
| 1 | Con la foto de Güembé (más clara que una ilustración), el título blanco de la portada quedaba sobre cielo y arbustos amarillos: 2,0:1 en 390 px y 2,7:1 en 1280 px (medición sobre capturas; Lighthouse no evalúa texto sobre imágenes) | WCAG 1.4.3 (3:1 para texto grande) | `.hero-texto` con 4rem de relleno superior y velo intermedio de 0,7 | 3,95:1 en 390 px, 4,6:1 en 1280 px, 8,6:1 en 768 px |
| 2 | El póster del video pesaba 225 KB (1280 × 720) y era el archivo más pesado de la portada (Lighthouse, network-requests) | Rendimiento | Póster a 960 × 540, JPEG calidad 72: 119 KB (alcanza para el video de 640 × 360 en pantallas de alta densidad) | Portada: rendimiento 93 → 97, LCP 3,2 → 2,6 s, peso 434 → 329 KiB |
| 3 | En la versión Bootstrap el menú y el pie seguían con los colores de Bootstrap: las clases `bg-body-tertiary`, `bg-body` y `bg-success-subtle` leen las variables `-rgb` y `--bs-success-*`, que no estaban definidas | Identidad de marca y contraste | Se agregaron `--bs-body-bg-rgb`, `--bs-tertiary-bg-rgb` y `--bs-success-*` en claro y en oscuro | Colores calculados: menú #e6efed y pie #d4eae8 (claro); #132427 y #10292b (oscuro) |
| 4 | `sitemap.xml`: la primera dirección empezaba con ` ttps://` (sin la "h" y con un espacio) | SEO técnico | Dirección corregida | Las 6 URL del sitemap empiezan con la dirección publicada |
| 5 | El mapa de contacto descarga ~300 KiB de scripts de Google Maps aunque tiene `loading="lazy"`: está a menos de la distancia de carga diferida | Rendimiento | Aceptado: el mapa aporta valor y la página igual obtiene 100 | Mejora pendiente: una fachada estática que cargue el iframe al tocarla |
| 6 | La página de práctica trae 9 problemas sembrados: título vago, sin description, colores sueltos sin contraste, salto de h1 a h4, imagen sin alt ni dimensiones, enlace "clic aquí", botón con solo un ícono y sin nombre, sin favicon (error 404 en la consola) | WCAG 1.1.1, 1.3.1, 1.4.3, 2.4.4, 4.1.2; SEO; CLS | Corregidos, con comentarios numerados en `practica-auditoria.html` | Lighthouse 100 / 100 / 100 / 100 en claro y oscuro |

Lección: la paleta propia se revisó color por color (32 combinaciones con contraste AA), pero el problema más grande
apareció en el texto sobre la foto, que ninguna herramienta automática mide. Por eso las dos revisiones son necesarias.

## 3. Validación W3C
- HTML (10 archivos: las 7 páginas del sitio, `404.html`, `version-bootstrap/index.html` y `practica-auditoria.html`):
  0 errores con html-validate (recommended + a11y).
- CSS: `css/estilos.css` 0 errores y 5 advertencias; las 5 dicen que las variables CSS no se pueden comprobar de forma
  estática, así que son falsos positivos. `version-bootstrap/css/personalizado.css`: 0 errores y 0 advertencias.

## 4. Pruebas manuales
| Prueba | Resultado |
|---|---|
| Teclado en la portada: menú, botón y enlaces de las tarjetas | ✔ foco visible de 3 px en todos, en orden de lectura |
| Teclado en el formulario | ✔ los 11 controles se alcanzan con Tab; el idioma del guía se elige con las flechas, como todo grupo de radio |
| Preguntas frecuentes (`<details>`) | ✔ se abren con Enter y se cierran con Espacio |
| Modal de la versión Bootstrap | ✔ se abre, Escape lo cierra y el foco vuelve a "Reserva rápida"; el carrusel no avanza solo |
| Zoom 200 % (1280 px → 640 px útiles) | ✔ sin desplazamiento horizontal en las 5 páginas públicas |
| Reflow 320 px (WCAG 1.4.10) | ✔ sin desplazamiento horizontal en las 9 páginas |
| Modo oscuro | ✔ 32 combinaciones de color con contraste AA; Lighthouse 100 en accesibilidad en oscuro |
| Movimiento reducido | ✔ con `reduce` la portada aparece sin animación y el salto a las anclas es inmediato |
| Lector de pantalla | Pendiente: no se probó con NVDA ni con el Narrador |

## 5. SEO técnico
canonical en las 6 páginas públicas ✔ · robots.txt con la línea Sitemap ✔ · sitemap.xml con 6 URL ✔ ·
JSON-LD TravelAgency (JSON válido, con los mismos datos que muestra el sitio) ✔ · 404.html con `<base>`, probada en una
ruta inexistente anidada ✔ · gracias.html y 404.html con noindex ✔

## 6. Sitio publicado (laboratorio 14)
Dirección: https://sahoneropenaalanrdorigo-web.github.io/senderos-guembe/ (GitHub Pages, rama `main`, carpeta raíz).

| Página | Rendimiento | Accesibilidad | Buenas prácticas | SEO | LCP | CLS | Peso |
|---|---|---|---|---|---|---|---|
| index | 99 | 100 | 100 | 100 | 1,8 s | 0 | 312 KiB |
| contacto | 100 | 100 | 100 | 100 | 1,1 s | 0 | 472 KiB |
| nosotros | 100 | 100 | 100 | 100 | 1,0 s | 0 | 9 KiB |

Medido el 26 de octubre de 2026 con Lighthouse 12.8 (móvil) contra la URL publicada; la API de PageSpeed Insights no
tenía cuota disponible ese día. Frente a la medición local, la portada pasa de 97 a 99 y su LCP de 2,6 a 1,8 s: GitHub
Pages comprime los archivos y los sirve desde su red de distribución.

Comprobaciones en línea: las 8 páginas, `sitemap.xml`, `robots.txt`, el CSS, el video y la imagen de Open Graph
responden 200; una dirección inexistente (`/senderos-guembe/no-existe/otra.html`) devuelve la página 404 propia con
código 404 y su `<base>`.

## 7. Conclusión
El sitio llega a 100 en accesibilidad, buenas prácticas y SEO en todas las páginas medidas, en claro y en oscuro, y a
96-100 en rendimiento en las páginas propias. Las fotos reales pesan más que las ilustraciones originales: la portada y
la galería tienen el LCP más alto (2,6 y 2,7 s en móvil simulado). La versión Bootstrap es la más pesada (543 KiB, 88 en
rendimiento) por el CSS y el JavaScript del framework. Quedan como mejoras la fachada del mapa y la prueba con lector
de pantalla.
