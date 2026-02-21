# Guía de Assets — Kakuaa Crecimiento

Esta carpeta almacena todos los recursos gráficos y multimedia del sitio.

```
/assets/
  ├── graphics/
  │   ├── dashboards/      ← GIFs/PNGs estáticos de dashboards
  │   ├── charts/          ← SVGs interactivos de gráficos
  │   └── icons/           ← Iconografía 2D/3D
  ├── video/
  │   └── demos/           ← Videos de demostraciones
  └── README.md            ← Esta guía
```

---

## Cómo Agregar Gráficos al Dashboard

### Opción 1: GIF Animado

- **Formato:** `.gif` o `.webp`
- **Peso recomendado:** ~500 KB – 2 MB
- **Uso ideal:** Demostraciones rápidas de pantallas y flujos
- **Almacenamiento:** `/assets/graphics/dashboards/`

**Cómo agregarlo:**
1. Coloca el archivo en `/assets/graphics/dashboards/mi-dashboard.gif`
2. En `kakuaa_crecimiento.html`, reemplaza la URL en la etiqueta `<img>`:

```html
<img src="assets/graphics/dashboards/mi-dashboard.gif"
     alt="Dashboard de análisis" loading="lazy">
```

---

### Opción 2: SVG Interactivo

- **Formato:** `.svg`
- **Peso recomendado:** 50 – 200 KB
- **Uso ideal:** Gráficos editables con mayor calidad visual
- **Almacenamiento:** `/assets/graphics/charts/`

**Cómo agregarlo (como imagen):**
```html
<img src="assets/graphics/charts/grafico-crecimiento.svg"
     alt="Gráfico de crecimiento" width="800" height="400">
```

**Cómo agregarlo (embed inline — más personalizable):**
```html
<!-- Pega el contenido del .svg directamente en el HTML -->
<svg viewBox="0 0 800 400" xmlns="http://www.w3.org/2000/svg">
  <!-- contenido del SVG -->
</svg>
```

---

### Opción 3: Embed de Plataformas (Tableau / Power BI / Looker Studio)

- **Plataformas:** Tableau Public, Power BI, Looker Studio (Google)
- **Almacenamiento:** Links externos (no se guardan archivos locales)
- **Uso ideal:** Dashboards actualizables en tiempo real

**Cómo agregarlo:**
1. En la plataforma correspondiente, selecciona **Compartir → Embed code**
2. Copia el código `<iframe>` generado
3. Pégalo en `kakuaa_crecimiento.html` dentro del contenedor del dashboard:

```html
<iframe src="https://public.tableau.com/views/MiDashboard/Sheet1?:embed=y"
        width="100%" height="480"
        frameborder="0"
        allowfullscreen
        title="Dashboard de Kakuaa"></iframe>
```

> **Nota:** Verifica que el dashboard sea público o que los permisos de iframe estén habilitados.

---

### Opción 4: Video MP4

- **Formato:** `.mp4` (codec H.264 recomendado)
- **Peso recomendado:** 5 – 20 MB (comprimido con HandBrake o similar)
- **Uso ideal:** Demostraciones complejas o animadas
- **Almacenamiento:** `/assets/video/demos/`

**Cómo agregarlo:**
1. Coloca el archivo en `/assets/video/demos/demo-dashboard.mp4`
2. En `kakuaa_crecimiento.html`, usa la etiqueta `<video>`:

```html
<video controls autoplay muted loop playsinline
       width="100%" style="border-radius: 12px;">
  <source src="assets/video/demos/demo-dashboard.mp4" type="video/mp4">
  Tu navegador no soporta el elemento de video.
</video>
```

> **Tip de accesibilidad:** Agrega siempre un `<track>` con subtítulos si el video contiene narración.

---

## Notas de Performance

| Formato | Tamaño típico | Carga | Editable |
|---------|--------------|-------|----------|
| GIF     | 500 KB–2 MB  | ⚡ Rápida | ❌ |
| WebP    | 100–500 KB   | ⚡⚡ Muy rápida | ❌ |
| SVG     | 50–200 KB    | ⚡⚡ Muy rápida | ✅ |
| MP4     | 5–20 MB      | 🔄 Streaming | ❌ |
| iFrame  | Externo      | 🌐 Depende del servicio | ✅ |

- Usa `loading="lazy"` en todas las etiquetas `<img>` fuera del viewport inicial.
- Comprime imágenes con [Squoosh](https://squoosh.app/) antes de subir.
- Usa `preload="none"` en videos que no estén en la sección visible al cargar.
