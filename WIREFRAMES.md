# Wireframes — Senderos Güembé

Laboratorio 12 (página "Nosotros") y Laboratorio 15 (portada). Se diseñan primero en celular y después en escritorio.

## 1. Arquitectura de información (mapa del sitio)
```
Inicio ─┬─ Tours ──── (anclas por tour: mariposario, fullday, aviario, monos, cabana, kayak) ─── Tarifas
        ├─ Galería
        ├─ Nosotros   ← nueva en el laboratorio 12
        ├─ Contacto ─── Formulario de reserva ─── Gracias
        └─ (pie) Políticas de reserva
404 (cualquier dirección que no existe) · version-bootstrap/ (prototipo de la portada)
```

## 2. "Nosotros" — celular (390 px), primero
```
┌───────────────────────────┐
│ Senderos Güembé           │  cabecera
│ Inicio Tours Galería      │
│ Nosotros Contacto         │
├───────────────────────────┤
│ NOSOTROS (h1)             │
│ Texto de entrada (quiénes │
│ somos y nuestra regla)    │
│                           │
│ Nuestra historia (h2)     │
│ ┃ ● 2014 primer grupo     │  línea de tiempo
│ ┃ ● 2017 certificación    │
│ ┃ ● 2020 árboles nativos  │
│ ┃ ● 2023 cabaña y kayak   │
│ ┃ ● 2026 este sitio       │
│                           │
│ El equipo (h2)            │
│ ┌───────────────────────┐ │
│ │  (RM)  Rosa Méndez    │ │  tarjeta por persona
│ │  guía del mariposario │ │  (1 columna)
│ └───────────────────────┘ │
│ …                         │
│ Nuestro impacto (h2)      │
│ [ +4.000 viajeros ]       │  cifras apiladas
│ [ 1.200 árboles   ]       │
│ [ 8 por grupo     ]       │
│                           │
│ Preguntas frecuentes (h2) │
│ ▸ ¿Necesito experiencia?  │  <details>
│ ▸ ¿Qué debo llevar?       │
│                           │
│ ( Reserva tu tour )       │  botón → contacto.html#reserva
└───────────────────────────┘
```

## 3. "Nosotros" — escritorio (1280 px)
```
┌────────────────────────────────────────────────────────────┐
│ Senderos Güembé                   Inicio Tours … Contacto  │ fija
├────────────────────────────────────────────────────────────┤
│ NOSOTROS                                                   │
│ Texto de entrada (máx. 65 caracteres por línea)            │
│                                                            │
│ Nuestra historia (sigue siendo vertical)                   │
│                                                            │
│ El equipo                                                  │
│ ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐   4 tarjetas en fila   │
│ │ (RM) │ │ (JM) │ │ (LM) │ │ (AV) │                        │
│ └──────┘ └──────┘ └──────┘ └──────┘                        │
│ Nuestro impacto                                            │
│ [ +4.000 ]   [ 1.200 ]   [ 8 ]          3 cifras en fila   │
│ Preguntas frecuentes (acordeón a todo el ancho)            │
└────────────────────────────────────────────────────────────┘
```

## 4. Portada — celular (390 px)
```
┌───────────────────────────┐
│ Senderos Güembé           │
│ Inicio Tours Galería …    │
├───────────────────────────┤
│ ┌───────────────────────┐ │
│ │ foto del sendero de   │ │  imagen de portada con el
│ │ la pérgola            │ │  texto encima, sobre un velo
│ │ DESCUBRE GÜEMBÉ (h1)  │ │  oscuro para el contraste
│ │ quiénes somos         │ │
│ │ ( Ver todos los tours)│ │  botón naranja
│ └───────────────────────┘ │
│ Tours destacados (h2)     │
│ [foto] Mariposario  Bs 220│  tarjetas apiladas
│ [foto] Full Day     Bs 380│
│ [foto] Aviario      Bs 200│
│ Güembé en 8 segundos      │  video con subtítulos
│ ¿Por qué elegirnos?       │
│                [WhatsApp] │  botón flotante
└───────────────────────────┘
```

## 5. Portada — escritorio (1280 px)
```
┌────────────────────────────────────────────────────────────┐
│ Senderos Güembé                  Inicio Tours … Contacto   │
├────────────────────────────────────────────────────────────┤
│ ┌────────────────────────────────────────────────────────┐ │
│ │ foto a todo el ancho                                   │ │
│ │ DESCUBRE GÜEMBÉ CON GUÍAS LOCALES (texto en 44rem)     │ │
│ │ ( Ver todos los tours )                                │ │
│ └────────────────────────────────────────────────────────┘ │
│ Tours destacados                                           │
│ ┌────────┐ ┌────────┐ ┌────────┐   3 tarjetas en fila      │
│ └────────┘ └────────┘ └────────┘                           │
│ Güembé en 8 segundos         ¿Por qué elegirnos?           │
└────────────────────────────────────────────────────────────┘
```

## 6. Decisiones
- Contenido primero: en "Nosotros" la historia va antes que el equipo porque genera confianza.
- Avatares con iniciales: no hay fotos del equipo con permiso de uso; se reemplazarán por fotos reales.
- Preguntas frecuentes con `<details>`: se abren con teclado sin JavaScript.
- Portada: el texto va sobre la foto con un velo turquesa oscuro; la foto de Güembé es clara (cielo y arbustos
  amarillos), así que el texto tiene 4rem de aire arriba para que el título quede siempre sobre la parte oscura.
- Colores: paleta "Laguna" (turquesa de las lagunas + naranja del tucán), con contraste AA en claro y en oscuro.
