# AutoVolt Energy — Sitio web

Sitio web oficial (landing público) de **AutoVolt Energy**. Presenta la propuesta
para **conductores** (app), **conjuntos residenciales**, **hoteles y hospitales**,
**centros comerciales**, **empresas/operadores** (importación e instalación de hardware)
y **operadores que licencian el software** (white-label), y aloja las páginas legales.

Es un sitio **100% estático**: HTML + CSS, sin framework ni paso de build.
Dentro del workspace vive en `Web/` y se despliega de forma independiente de la
plataforma operativa (`../Operativo/`) para que publicar marketing no toque backend,
dashboard, app ni infraestructura de producción.

Producción: **https://www.autovoltenergy.net** (GitHub Pages)

## Stack

| Capa | Tecnología |
|---|---|
| Marcado | HTML5 |
| Estilos | CSS plano (variables nativas, sin preprocesador) |
| Tipografía | Inter (Google Fonts) |
| JS | Mínimo, inline (año del footer) |
| Build | Ninguno — se sirven los archivos tal cual |
| Hosting | GitHub Pages |

## Estructura

| Archivo | Propósito |
|---|---|
| `index.html` | Landing principal (hub de soluciones: conjuntos residenciales, centros comerciales, hoteles y hospitales, empresas/operadores, software; sección de conductores y contacto) |
| `cargadores-conjuntos-residenciales.html` | Modelo anfitrión sujeto a prefactibilidad: la copropiedad puede elegir participación de ingresos o tarifa preferencial. 100% residencial, carga lenta AC de 7 kW |
| `cargadores-centros-comerciales.html` | Modelo anfitrión para sitios de alta afluencia: espacio + conexión; comisión definida por contrato. Carga rápida DC desde 20 kW |
| `cargadores-hoteles-hospitales.html` | Modelo anfitrión para hoteles y hospitales: AC 7 kW (huéspedes) o DC desde 20 kW (visitantes/personal), según evaluación del sitio |
| `soluciones-para-empresas.html` | Página comercial: 2 líneas para empresas/operadores (importación de hardware + instalación). Cruza a la página de software para la plataforma |
| `software-para-electrolineras.html` | Página comercial: licencia white-label del software CPO (keyword principal). El operador opera con su propia marca, app y pasarela de pago |
| `como-poner-cargadores-en-mi-conjunto.html` | Guía SEO (top-of-funnel) que enlaza a la página comercial de conjuntos |
| `terminos.html` | Términos y Condiciones |
| `privacidad.html` | Política de Privacidad y Tratamiento de Datos |
| `styles.css` | Hoja de estilos compartida |
| `sitemap.xml` | Mapa del sitio para buscadores |
| `robots.txt` | Directivas de rastreo + referencia al sitemap |
| `CNAME` | Dominio personalizado para GitHub Pages (`www.autovoltenergy.net`) |
| `google6258b155e64498e9.html` | Archivo de verificación de Google Search Console. No eliminar mientras se use ese método |
| `.nojekyll` | Desactiva el procesamiento Jekyll de GitHub Pages |
| `assets/` | Logo (transparente y 4K) e isotipo (favicon) |

## SEO y captación

Dominio canónico: **`https://www.autovoltenergy.net`** (todas las `<link rel="canonical">`,
`og:url` y el `sitemap.xml` apuntan ahí).

- **Estrategia:** una página por intención de búsqueda (conjuntos residenciales, centros comerciales, hoteles y hospitales, empresas/operadores, software).
- **Datos estructurados (JSON-LD):** `Organization` (home); `Service`, `BreadcrumbList`
  y `FAQPage` en las páginas comerciales; `Article` en la guía.
- **Conversión:** botón flotante de WhatsApp (`+57 314 490 7237`) en todas las páginas + CTA por WhatsApp/correo.
- **Contacto:** buzón único `gerencia@autovoltenergy.net`.

## Contenido comercial (promesas defendibles)

Revisión final de contenido (2026-06-14): todas las páginas comerciales se redactaron
para que **ninguna promesa quede sin respaldo**. El principio editorial es que cada
afirmación de modelo, ingreso o instalación sea **defendible** ante un comité de
copropiedad, un centro comercial o una empresa.

- **Todo va condicionado a prefactibilidad** técnica, eléctrica, económica y contractual.
  No se promete instalación ni rentabilidad sin evaluar capacidad, flujo, costos e inversión.
- **Sin cifras de comisión fijas en el sitio:** el porcentaje y la liquidación se definen
  **por contrato** según flujo, costos de energía, inversión y condiciones del sitio
  (se eliminó el rango `7,5%–20%` que antes aparecía publicado).
- **Conjuntos residenciales:** el modelo anfitrión busca cero inversión inicial *en proyectos
  aprobados*; la copropiedad puede elegir participación de ingresos **o** tarifa preferencial
  para residentes, sujeto a costos de energía y contrato. Foco 100% residencial, carga lenta AC de 7 kW.
- **Hoteles y hospitales:** modelo anfitrión para sitios de alta rotación; AC de 7 kW (huéspedes)
  o DC desde 20 kW (visitantes/personal), según evaluación del sitio (flujo, plazas, capacidad eléctrica).
- **Centros comerciales:** se enmarca como modelo a comisión definida por contrato, con
  carga rápida (DC desde 20 kW) solo donde la capacidad y el flujo lo justifiquen.
- **Empresas/operadores:** dos líneas (importación de hardware + instalación) sujetas a alcance,
  permisos y compatibilidad (p. ej. OCPP 1.6-J). La plataforma se ofrece aparte, en la página de software.
- **Software (operadores):** se ofrece como **licencia white-label**: el operador licencia la
  plataforma CPO y la opera con su propia marca, su app (con el nombre de su empresa), sus tarifas,
  sus conductores y su propia pasarela de pago. AutoVolt cobra licencia (setup + recurrente), sin
  comisión sobre las cargas.

Al editar estas páginas, mantener este criterio: preferir verbos como *evaluamos, cotizamos,
proponemos* y condicionantes (*sujeto a, según contrato, cuando el flujo lo justifique*)
en lugar de promesas absolutas o cifras cerradas.

## Desarrollo local

No requiere instalación. Desde la raíz del workspace:

```bash
npm run web:serve        # luego abrir http://localhost:8080
```

O desde esta carpeta, sirve los archivos con cualquier servidor estático:

```bash
python -m http.server 8080      # luego abrir http://localhost:8080
```

O abre `index.html` directamente en el navegador.

## Despliegue (GitHub Pages)

1. Publica el contenido de `Web/` como raíz del repositorio de GitHub Pages (p. ej. `autovolt-web`) y haz push a la rama `main`.
2. En **Settings → Pages**: *Source* = **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. El archivo `CNAME` ya fija el dominio `www.autovoltenergy.net`. En **Settings → Pages → Custom domain** debe quedar verificado.
4. En Squarespace DNS, crea un registro **CNAME**: `www` → `morpheus8810-blip.github.io`.
5. Activa **Enforce HTTPS** una vez propague el dominio.

Cada push a `main` republica el sitio automáticamente. No depende de `Operativo/` ni del deploy a Hetzner.

### Estado verificado 2026-06-14

| Punto | Estado |
|---|---|
| Repo remoto | `https://github.com/morpheus8810-blip/autovolt-web.git` |
| Rama | `main` |
| `CNAME` | `www.autovoltenergy.net` |
| GitHub Pages | `morpheus8810-blip.github.io/autovolt-web` redirige al dominio personalizado |
| DNS actual | `www.autovoltenergy.net` resuelve a `morpheus8810-blip.github.io` |
| DNS pendiente | Ninguno para `www` |
| HTTPS | Activo: `https://www.autovoltenergy.net/` responde `200 OK` |
| Enforce HTTPS | Pendiente: `http://www.autovoltenergy.net/` aún responde `200 OK` sin redirigir |

### Estado SEO 2026-06-14

| Punto | Estado |
|---|---|
| Search Console | Propiedad verificada por archivo HTML |
| Verificación | `google6258b155e64498e9.html` publicado en la raíz del sitio |
| `robots.txt` | Activo y apunta a `https://www.autovoltenergy.net/sitemap.xml` |
| `sitemap.xml` | Enviado y leído como correcto; 9 páginas (incluye hoteles y hospitales) |
| Analítica/cookies | Sin scripts de tracking por ahora |
| Perfil de Empresa de Google | Pendiente. Crear como negocio virtual/área de servicio, sin dirección visible |

## Pendientes

- **Cumplimiento:** revisar y cerrar `../PLAN-DE-AVANCE.md` antes de publicar la app,
  cobrar sesiones o instalar estaciones de acceso público.
- **Placeholders legales:** `[NIT]`, `[DIRECCIÓN COMERCIAL]`, `[CIUDAD]` y `[FECHA DE VIGENCIA]`
  siguen pendientes en `terminos.html` y `privacidad.html` hasta tener datos oficiales.
- **SEO local:** crear/actualizar el Perfil de Empresa de Google como negocio virtual/área de servicio,
  sin dirección visible hasta tener sede o estación pública real.
- **Analítica:** no instalar scripts de tracking/cookies por ahora. Usar Search Console primero;
  GA4/Meta Pixel/Hotjar/Plausible quedan para después de aprobar privacidad y aviso/capa de cookies si aplica.
- **Badges de tiendas:** Google Play / App Store quedan como elementos visuales no clicables hasta publicar las apps.
