# Resoria Landing Page

Landing page estática y bilingüe para **Resoria**, empresa de software con dos productos:

- **Easy Restaurant** — gestión de restaurantes, cafeterías y food trucks
- **Mi Inventario** — control de stock para tiendas, bodegas y almacenes

El sitio presenta los productos, precios (licencia de por vida y SaaS), comparativa de modalidades, casos de éxito, contacto y páginas de detalle por producto.

## Stack tecnológico

| Tecnología | Uso |
|------------|-----|
| [Astro 6](https://astro.build) | Framework, generación estática |
| [Tailwind CSS v4](https://tailwindcss.com) | Estilos |
| [@astrojs/sitemap](https://docs.astro.build/en/guides/integrations-guide/sitemap/) | Sitemap XML |
| TypeScript | Tipos de contenido |
| pnpm | Gestor de paquetes |

**Requisitos:** Node.js `>=22.12.0` y pnpm.

## Rutas

| Ruta | Descripción |
|------|-------------|
| `/` | Redirige a `/es/` |
| `/es/` | Home en español |
| `/en/` | Home en inglés |
| `/es/productos/easy-restaurant/` | Detalle Easy Restaurant (ES) |
| `/es/productos/mi-inventario/` | Detalle Mi Inventario (ES) |
| `/en/productos/easy-restaurant/` | Detalle Easy Restaurant (EN) |
| `/en/productos/mi-inventario/` | Detalle Mi Inventario (EN) |
| `/es/privacidad/` | Política de privacidad (ES) |
| `/es/terminos/` | Términos y condiciones (ES) |
| `/en/privacy/` | Privacy policy (EN) |
| `/en/terms/` | Terms and conditions (EN) |

## Estructura del proyecto

```text
/
├── public/
│   ├── logos/          # Logos de Resoria y productos
│   ├── favicon.svg
│   └── robots.txt
├── src/
│   ├── components/     # UI: Hero, Header, ProductPricing, ProductDetailPage, etc.
│   ├── content/
│   │   ├── es.json     # Textos de la home (ES)
│   │   ├── en.json     # Textos de la home (EN)
│   │   ├── legal/      # Privacidad y términos (ES/EN)
│   │   └── product-details/  # Contenido de páginas de producto
│   ├── layouts/        # BaseLayout (SEO, header, footer)
│   ├── lib/            # Carga de contenido y utilidades
│   ├── pages/          # Rutas Astro
│   ├── scripts/        # typewriter, scroll-reveal, youtube-embed
│   ├── styles/         # global.css (tema y utilidades)
│   └── types/          # Tipos TypeScript del contenido
├── astro.config.mjs
└── package.json
```

## Comandos

```bash
# Instalar dependencias
pnpm install

# Servidor de desarrollo (http://localhost:4321)
pnpm dev

# Build de producción → ./dist/
pnpm build

# Previsualizar el build localmente
pnpm preview
```

## Contenido editable

La mayoría del copy vive en JSON, sin tocar componentes:

| Archivo | Qué editar |
|---------|------------|
| `src/content/es.json` / `en.json` | Home: hero, productos, precios, contacto, footer |
| `src/content/product-details/es/*.json` | Páginas de detalle en español |
| `src/content/product-details/en/*.json` | Páginas de detalle en inglés |
| `src/content/legal/es/*.json` | Privacidad y términos (ES) |
| `src/content/legal/en/*.json` | Privacidad y términos (EN) |
| `astro.config.mjs` | URL del sitio (`site`) para SEO y sitemap |
| `public/logos/` | Logos e imágenes estáticas |

### Precios y productos

Los planes (licencia / SaaS) se definen en `es.json` y `en.json` bajo `products`. Las páginas de detalle reutilizan esos mismos datos para la sección de ofertas al final.

### Videos de YouTube

Los embeds usan **click-to-play** (`YouTubeEmbed.astro`) para no cargar iframes hasta que el usuario pulse play. Sustituye `videoId` en los JSON cuando tengas los videos reales.

### Enlaces de descarga

Mientras `downloadUrl` sea `"#"`, el botón «Descargar / Gratis» no navega (placeholder). Pon la URL real del instalador o tienda cuando esté lista.

## SEO e internacionalización

- Rutas con prefijo de idioma (`/es/`, `/en/`)
- Meta tags, Open Graph y Twitter Cards (`Seo.astro`)
- `hreflang` y canonical por página
- JSON-LD: `Organization` + `SoftwareApplication` por producto
- Sitemap generado en el build

## Características de la UI

- Navbar con anclas en la home (oculta en páginas de producto)
- Hero con typewriter animado
- Tarjetas de beneficios y «Cómo funciona» con imágenes
- Casos de éxito con video y testimonio
- Comparativa licencia vs SaaS
- Formulario de contacto (listo para conectar con Formspree, Netlify Forms, etc.)
- Animaciones de scroll con respeto a `prefers-reduced-motion`

## Despliegue

El proyecto genera HTML estático en `dist/`. Puedes publicarlo en:

- **GitHub Pages**
- **Netlify / Vercel / Cloudflare Pages**
- Cualquier hosting de archivos estáticos

Antes de desplegar, actualiza la URL en `astro.config.mjs`:

```js
const SITE_URL = 'https://resoria.com'; // tu dominio real
```

Si usas **GitHub Pages** con un repositorio de proyecto (no `usuario.github.io`), también necesitarás configurar `base: '/nombre-del-repo/'` en `astro.config.mjs`.

## Licencia

Proyecto privado de Resoria. Todos los derechos reservados.
