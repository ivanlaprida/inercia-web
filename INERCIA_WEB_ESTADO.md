# Sitio Web Inercia — Documento de estado

**Última actualización:** Junio 2026  
**Carpeta del proyecto:** `C:\Users\hp\Claude\Projects\Sitio Web\`

---

## Resumen

Sitio web estático de una sola página (`index.html`) para **Inercia**, fábrica de muebles a medida en Buenos Aires. Estética minimalista/moderna. Funciona abriéndolo directamente en el navegador o subiéndolo a un hosting.

**Dominio comprado:** GoDaddy (pendiente de publicar).  
**Hosting recomendado:** Netlify (gratis para sitios estáticos — arrastrar la carpeta al panel).

---

## Archivos principales

| Archivo | Descripción |
|---|---|
| `index.html` | Todo el sitio: HTML + CSS + JS en un solo archivo |
| `Logo_inercia_1_t.png` | Logo PNG con fondo transparente. En el nav se recorta solo el círculo |
| `INERCIA - DESARROLLOS.pdf` | Presentación comercial para desarrolladores, descargable desde la tarjeta "Desarrollos" |
| `DESARROLLOS/page-04.jpg` ... `page-19.jpg` | Páginas del PDF convertidas a JPG, usadas en el lightbox de Desarrollos |

---

## Carpetas de proyectos (portfolio)

Todas las fotos fueron comprimidas a máx. 1920px / calidad 78% con ImageMagick.

| Carpeta | Fotos | Categoría en lightbox |
|---|---|---|
| PIROVANO | 7 | Cocina a medida · 2024 |
| EL TREBOL | 20 (aprox) | Cocina a medida · 2024 |
| MARTINDALE | 5 | Cocina clásica · 2024 |
| SANTA BARBARA | 6 | Vestidor · 2022 |
| SUCRE | 9 | Cocina a medida · 2023 |
| SAN JORGE I | 7 | Cocina a medida · 2023 |
| LAPRIDA | 8 | Vestidor · 2023 |
| ALTO PERU | 10 | Cocina a medida · 2023 |
| BARBARITA | 9 | Vestidor · 2023 |
| LAS HERAS | 49 | Cocina a medida · 2024 |
| COLEGIO COPELLO | 20 | Proyecto comercial · 2024 |
| MANZANARES | 15 | Cocina a medida · 2023 |
| PINGUINOS CC | 5 | Cocina a medida · 2023 |
| SAN SEBASTIAN | 4 | Cocina a medida · 2022 |
| VICENTE LOPEZ I | 5 | Vestidor · 2022 |

La carpeta `Fotos Web/` tiene fotos del equipo (IMG_5759.jpg, IMG_9856.jpg, IMG_4078.JPG) — ya no se usan en el sitio (sección Nosotros quedó solo texto).

---

## Secciones del sitio

### 1. Nav (fijo, 56px de alto)
- Logo: solo el círculo del PNG, recortado con `overflow:hidden` y márgenes negativos
- Texto "INERCIA" a la derecha del logo
- Links: Servicios · Portfolio · Nosotros · Testimonios · Contacto (botón negro)

### 2. Hero
- Eyebrow: "Buenos Aires · Hecho a Mano · 2019"
- Foto de fondo: `PIROVANO/IMG_9858.jpg`
- Título grande con Playfair Display

### 3. Servicios (fondo negro)
- 4 tarjetas en grid: **01 Cocinas · 02 Vestidores · 03 Muebles de Diseño · 04 Desarrollos**
- Cada tarjeta abre un lightbox con fotos de esa categoría
- Desarrollos tiene además un link `↓ Presentación` que descarga el PDF

### 4. Portfolio
- Grid CSS asimétrico: `2fr 1fr 1fr` en columnas, con primer item que ocupa 2 filas
- 15 proyectos, cada uno abre lightbox con todas sus fotos
- Lightbox tiene: imagen grande, miniaturas abajo, navegación con flechas y teclado

### 5. Quiénes Somos (Nosotros)
- Sin fotos (se eliminaron)
- Eyebrow: "Quiénes somos"
- Título: "Creamos muebles a medida. Diseñamos experiencias de principio a fin."
- 4 párrafos de texto (el último en itálica dorada)
- Stats: +40 personas · 100% proyectos a medida · 237 proyectos ejecutados · ARG fabricación nacional

### 6. Testimonios (fondo oscuro)
- 4 tarjetas:
  - Guadalupe Diez — Obra Laprida
  - Carlos Darmandrail, Ing. — Zanara S.A.
  - Augusto Soldati — Sureniio
  - Alejandra Carregal — Clienta

### 7. Contacto
- Email: info@inerciaba.com
- WhatsApp: +5491138745762 (link a wa.me)
- Instagram: @inercia.ba (link a instagram.com/inercia.ba)

### 8. Footer
- Logo invertido (blanco), links de navegación, © 2026

---

## Variables de diseño (CSS)

```css
--black: #111111
--white: #FAFAF8
--gray: #6B6B6B
--light-gray: #E8E6E0
--warm: #C4A882   /* dorado claro — eyebrows, detalles */
--accent: #8B6F47 /* dorado oscuro — hover, itálicas */
```

**Tipografías:** Inter (cuerpo) + Playfair Display (títulos) — vía Google Fonts  
**Tamaño section-title:** `clamp(22px, 2.5vw, 34px)`  
**Tamaño testimonio-texto:** `15px` (Playfair Display, itálica)

---

## Pendientes / próximos pasos

- [ ] Publicar en Netlify y conectar dominio de GoDaddy
- [ ] Agregar Google Analytics (2 líneas en el `<head>`)
- [ ] Agregar más testimonios cuando estén disponibles
- [ ] Eventuamente agregar más proyectos al portfolio (sumar carpeta + línea en el HTML)

---

## Cómo agregar un proyecto al portfolio

1. Crear carpeta con las fotos en `C:\Users\hp\Claude\Projects\Sitio Web\NOMBRE_PROYECTO\`
2. En `index.html`, dentro del div `<!-- PORTFOLIO -->`, copiar un bloque `.portfolio-item` existente y cambiar:
   - La imagen de tapa (`<img src="...">`)
   - El título en el overlay
   - El array de imágenes en `openLightbox(...)`
3. El grid se ajusta automáticamente (`grid-auto-rows: 280px`)

## Cómo publicar el sitio

1. Crear cuenta en netlify.com
2. "Add new site" → "Deploy manually" → arrastrar la carpeta `Sitio Web` completa
3. En "Domain management" → agregar el dominio de GoDaddy
4. En GoDaddy: DNS → Nameservers → Personalizado → pegar los nameservers de Netlify
5. Esperar hasta 1 hora para que propague
6. HTTPS se activa solo
