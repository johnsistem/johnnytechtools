# Plan de Refactorización: Arquitectura Multi-Página para SEO (Johnny Tech Tools)

## Objetivo
Separar la landing actual (que tiene todo concentrado en una sola página `index.html`) en una **arquitectura multi-página orientada a SEO**. Cada herramienta tendrá su propia URL dedicada, con metadatos específicos, schema markup de software, contenido enfocado y palabras clave segmentadas, mientras que la portada (`index.html`) actuará como Hub principal de la suite.

---

## 1. Estructura de URLs Propuesta

```text
https://johnnytechtools.vercel.app/
├── index.html                  -> Hub / Portal principal (Suite de Herramientas)
├── excel2forms.html            -> Página dedicada para Excel2Forms (Extensión Chrome)
├── aid.html                    -> Página dedicada para AID (Asistente de Ingreso de Datos)
├── videofrases.html            -> Página dedicada para VideoFrases (Generador de Videos IA)
├── sitemap.xml                 -> Actualizado con las 4 URLs y prioridades
├── robots.txt                  -> Permitiendo rastreo de todas las páginas
└── google4ad121254d2d3672.html -> Verificación Search Console (permanece en raíz)
```

---

## 2. Estrategia SEO por Página

### A. Portada (`/index.html`) — Brand Hub
* **Meta Title**: `Johnny Q | Tech Tools — Suite de Herramientas de Productividad y Automatización`
* **Meta Description**: `Herramientas gratuitas para automatizar tareas repetitivas, ingreso de datos desde Excel y aprendizaje de inglés con IA. 100% locales y seguras.`
* **Contenido**:
  * Hero institucional fuerte.
  * Tarjetas de herramientas destacadas que enlazan con botón **"Conocer más"** hacia `/excel2forms.html`, `/aid.html` y `/videofrases.html`.
  * Sección sobre Johnny Q / Desarrollador, seguridad y privacidad (100% offline/local).
  * FAQ general y footer con navegación completa.

### B. `/excel2forms.html` — Keyword Target: "Autollenado de formularios desde Excel"
* **Meta Title**: `Excel2Forms — Extensión de Chrome para Autollenado de Formularios Web desde Excel`
* **Meta Description**: `Rellena y envía automáticamente formularios web complejos desde tus hojas de cálculo Excel o CSV. Extensión de Chrome gratis y segura.`
* **Keywords**: `automatizar formularios web, excel a web form, autollenar formulario chrome, extension excel chrome`
* **Schema JSON-LD**: `SoftwareApplication` (ApplicationCategory: BrowserApplication, OperatingSystem: Chrome, price: 0).
* **Contenido**:
  * Demostración en video embebida.
  * Botón directo a Chrome Web Store.
  * Guía paso a paso: cómo cargar el archivo, mapear campos y ejecutar el llenado.
  * Casos de uso y testimonios / FAQ específica de Excel2Forms.

### C. `/aid.html` — Keyword Target: "Asistente de Ingreso de Datos Offline"
* **Meta Title**: `AID (Asistente de Ingreso de Datos) — Automatización de Formularios 100% Offline`
* **Meta Description**: `Automatiza el ingreso masivo de datos en sistemas web y portales gubernamentales desde Excel con 3 modos de llenado. Privacidad total 100% local.`
* **Keywords**: `asistente de datos excel, autollenado offline, ingresar datos masivos formulario, data entry automation`
* **Schema JSON-LD**: `SoftwareApplication` (ApplicationCategory: BrowserApplication, OperatingSystem: Chrome).
* **Contenido**:
  * Detalle de los 3 modos de llenado.
  * Énfasis en privacidad y funcionamiento sin internet / datos confidenciales.
  * Demostración en video.

### D. `/videofrases.html` — Keyword Target: "Generador de Videos para Aprender Inglés"
* **Meta Title**: `VideoFrases — Genera Videos con Frases e IA para Aprender Inglés`
* **Meta Description**: `Aprende inglés técnico y conversacional. Genera videos con audio nativo, pronunciación y contexto para Devs, Negocios y Viajes.`
* **Keywords**: `aprender ingles devs, video frases ingles ia, generador videos ingles, ingles para programadores`
* **Schema JSON-LD**: `SoftwareApplication` (ApplicationCategory: MultimediaApplication, OperatingSystem: Web).
* **Contenido**:
  * Categorías temáticas (Dev, Business, Travel, Job Interview).
  * Enlace a la app web (`videofrases.onrender.com`).
  * Muestra visual y ejemplos de frases.

---

## 3. Elementos Globales y Consistencia
1. **Navegación / Header común**:
   * Logo Johnny Q | Tech Tools enlazando siempre a `index.html`.
   * Enlaces en menú: *Inicio*, *Excel2Forms*, *AID*, *VideoFrases*.
   * Toggle de idioma (ES / EN) mantenido y consistente en cada página.
2. **Footer común**:
   * Enlaces directos a cada una de las 3 herramientas.
   * Información legal / contacto / GitHub.
3. **Internal Linking (SEO Interlinking)**:
   * Cada página de herramienta tendrá una sección al final: *"Otras herramientas que te pueden interesar"* enlazando a las otras dos páginas para distribuir el link equity.

---

## 4. Archivos Técnicos SEO a Actualizar
* **`sitemap.xml`**:
  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
    <url>
      <loc>https://johnnytechtools.vercel.app/</loc>
      <changefreq>weekly</changefreq>
      <priority>1.0</priority>
    </url>
    <url>
      <loc>https://johnnytechtools.vercel.app/excel2forms.html</loc>
      <changefreq>monthly</changefreq>
      <priority>0.9</priority>
    </url>
    <url>
      <loc>https://johnnytechtools.vercel.app/aid.html</loc>
      <changefreq>monthly</changefreq>
      <priority>0.8</priority>
    </url>
    <url>
      <loc>https://johnnytechtools.vercel.app/videofrases.html</loc>
      <changefreq>monthly</changefreq>
      <priority>0.8</priority>
    </url>
  </urlset>
  ```

---

## 5. Pasos de Ejecución (Al abrir el nuevo proyecto)
1. [ ] Crear `excel2forms.html` extrayendo y expandiendo la sección de Excel2Forms.
2. [ ] Crear `aid.html` extrayendo y expandiendo la sección de AID.
3. [ ] Crear `videofrases.html` extrayendo y expandiendo la sección de VideoFrases.
4. [ ] Refactorizar `index.html` para convertirlo en un Hub limpio que enlaza a las subpáginas.
5. [ ] Actualizar `sitemap.xml` con las nuevas rutas.
6. [ ] Probar navegación, responsiveness y selector de idioma en local.
7. [ ] Hacer `git commit`, `git push` para que Vercel despliegue las nuevas páginas automáticamente.
