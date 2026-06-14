# AutoVolt Energy — Sitio web

Sitio web oficial (landing público) de **AutoVolt Energy**. Presenta la propuesta
para **conductores** (app), para **copropiedades y hoteles**, para **centros
comerciales** y para **operadores** (software multioperador), y aloja las páginas
legales.

Es un sitio **100% estático**: HTML + CSS, sin framework ni paso de build.
Repositorio **independiente** de la plataforma operativa (backend, dashboard, app),
para que su despliegue no toque la infraestructura de producción.

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
| `index.html` | Landing principal (conductores, conjuntos, centros comerciales, empresas, plataforma, contacto) |
| `cargadores-conjuntos-residenciales.html` | Modelo anfitrión: CPO instala sin costo; la copropiedad elige ingreso o energía más barata. Foco carga lenta |
| `cargadores-centros-comerciales.html` | Modelo anfitrión: el sitio aporta espacio y conexión; AutoVolt el punto de carga rápida; comisión 7,5%–20% sobre neto |
| `soluciones-para-empresas.html` | Página comercial: 3 líneas para empresas/operadores (importación, instalación, plataforma) + llave en mano |
| `software-para-electrolineras.html` | Página comercial: software/plataforma CPO (keyword principal) |
| `como-poner-cargadores-en-mi-conjunto.html` | Guía SEO (top-of-funnel) que enlaza a la página comercial de conjuntos |
| `terminos.html` | Términos y Condiciones |
| `privacidad.html` | Política de Privacidad y Tratamiento de Datos |
| `PENDIENTES-CUMPLIMIENTO.md` | Checklist operativo/legal/técnico antes de publicar app, cobrar o instalar estaciones públicas |
| `styles.css` | Hoja de estilos compartida |
| `sitemap.xml` | Mapa del sitio para buscadores |
| `robots.txt` | Directivas de rastreo + referencia al sitemap |
| `CNAME` | Dominio personalizado para GitHub Pages (`www.autovoltenergy.net`) |
| `.nojekyll` | Desactiva el procesamiento Jekyll de GitHub Pages |
| `assets/` | Logo (transparente y 4K) e isotipo (favicon) |

## SEO y captación

Dominio canónico: **`https://www.autovoltenergy.net`** (todas las `<link rel="canonical">`,
`og:url` y el `sitemap.xml` apuntan ahí).

- **Estrategia:** una página por intención de búsqueda (conjuntos, centros comerciales, software).
- **Datos estructurados (JSON-LD):** `Organization` (home); `Service`, `BreadcrumbList`
  y `FAQPage` en las páginas comerciales; `Article` en la guía.
- **Conversión:** botón flotante de WhatsApp (`+57 314 490 7237`) en todas las páginas + CTA por WhatsApp/correo.
- **Contacto:** buzón único `gerencia@autovoltenergy.net`.

## Desarrollo local

No requiere instalación. Sirve la carpeta con cualquier servidor estático:

```bash
python -m http.server 8080      # luego abrir http://localhost:8080
```

O abre `index.html` directamente en el navegador.

## Despliegue (GitHub Pages)

1. Crea el repositorio en GitHub (p. ej. `autovolt-web`) y haz push de esta carpeta a la rama `main`.
2. En **Settings → Pages**: *Source* = **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. El archivo `CNAME` ya fija el dominio `www.autovoltenergy.net`. En **Settings → Pages → Custom domain** debe quedar verificado.
4. En tu DNS, crea un registro **CNAME**: `www` → `TU_USUARIO.github.io`.
5. Activa **Enforce HTTPS** una vez propague el dominio.

Cada push a `main` republica el sitio automáticamente. No depende del repo operativo ni del deploy a Hetzner.

## Pendientes

- **Cumplimiento:** revisar y cerrar `PENDIENTES-CUMPLIMIENTO.md` antes de publicar la app,
  cobrar sesiones o instalar estaciones de acceso público.
- **Placeholders legales:** `[NIT]`, `[DIRECCIÓN COMERCIAL]`, `[CIUDAD]` y `[FECHA DE VIGENCIA]`
  siguen pendientes en `terminos.html` y `privacidad.html` hasta tener datos oficiales.
- **Search Console / analítica:** dar de alta el sitio en Google Search Console, enviar `sitemap.xml`,
  crear el Perfil de Empresa de Google y añadir analítica solo después de definir aviso/capa de cookies si aplica.
- **Badges de tiendas:** Google Play / App Store quedan como elementos visuales no clicables hasta publicar las apps.
