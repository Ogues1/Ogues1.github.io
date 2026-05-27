# Ogues1.github.io — Kakuaa Crecimiento

Sitio web de [kakuaa.me](https://kakuaa.me) — Plataforma de Inteligencia de Negocios.

## Archivos principales

| Archivo | Descripción |
|---------|-------------|
| `kakuaa_crecimiento.html` | Página principal con dashboard interactivo, iconografía 2D/3D y guía de assets |
| `assets/README.md` | Guía detallada para agregar gráficos propios al dashboard |

## Cómo agregar gráficos al dashboard

El dashboard en `kakuaa_crecimiento.html` incluye gráficos de ejemplo generados con [Chart.js](https://www.chartjs.org/).  
Para reemplazarlos con tus propios datos, consulta **[assets/README.md](assets/README.md)** donde encontrarás instrucciones para las 4 opciones disponibles:

1. **GIF / WebP** — Animaciones estáticas ligeras → `assets/graphics/dashboards/`
2. **SVG** — Gráficos vectoriales editables → `assets/graphics/charts/`
3. **Embed de BI** — Tableau, Power BI, Looker Studio (iframe externo)
4. **Video MP4** — Demos complejas → `assets/video/demos/`

## Estructura de carpetas

```
/
├── kakuaa_crecimiento.html   ← Página principal
├── assets/
│   ├── graphics/
│   │   ├── dashboards/       ← GIFs / PNGs de dashboards
│   │   ├── charts/           ← SVGs interactivos
│   │   └── icons/            ← Iconografía
│   ├── video/
│   │   └── demos/            ← Videos .mp4
│   └── README.md             ← Guía completa de assets
└── README.md                 ← Este archivo
```

## Características técnicas

- **Chart.js 4** — gráficos de líneas, barras, donas y área
- **CSS 3D transforms** — efecto de profundidad en tarjetas al hover
- **IntersectionObserver** — animación de barras de crecimiento al hacer scroll
- **Responsive / mobile-first** — hamburger menu en pantallas < 900 px
- **WCAG 2.1** — skip link, roles ARIA, labels accesibles, foco visible
- **Patrón F de escaneo** — logo+nav a la izquierda, botones CTA a la derecha