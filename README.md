# Resoria

**Software simple para hacer crecer tu negocio.**

Resoria desarrolla soluciones pensadas para dueños y equipos que necesitan herramientas claras, sin complicaciones. Esta landing presenta nuestra oferta de productos, precios y formas de contacto.

## Productos

### Easy Restaurant
Sistema para restaurantes, cafeterías, pizzerías, bares y food trucks. Centraliza mesas, comandas, cocina y caja en un solo lugar para servir más rápido y con menos errores.

### Mi Inventario
Software de control de stock para tiendas, bodegas, ferreterías, farmacias y almacenes. Registra entradas y salidas, recibe alertas de reposición y consulta reportes para tomar mejores decisiones.

## Modalidades

Cada producto está disponible en dos formatos:

- **Licencia de por vida** — pago único, instalación en tu equipo
- **SaaS mensual** — acceso desde cualquier dispositivo, actualizaciones incluidas

También ofrecemos **prueba gratuita de 15 días** para que conozcas el software antes de comprar.

## Sitio web

Landing bilingüe (**español** e **inglés**) con:

- Presentación de productos y precios
- Páginas de detalle con beneficios, tutoriales y casos de éxito
- Comparativa entre licencia y suscripción
- Formulario de contacto y métodos de pago
- Política de privacidad y términos de uso

## Contacto

Visita la sección de contacto en el sitio para solicitar información, una demo o adquirir una licencia.

## Publicación

Sitio publicado en **https://resorias.com** (GitHub Pages + dominio personalizado).

El repositorio no incluye `dist/`; GitHub Actions compila y despliega al hacer push a `master`.

### Configurar DNS en tu proveedor de dominio

En el panel DNS de **resorias.com**, crea estos registros ([guía de GitHub Pages](https://docs.github.com/es/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)):

**Dominio raíz (`resorias.com`)** — 4 registros tipo **A**:

| Tipo | Nombre | Valor |
|------|--------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

**Subdominio `www` (recomendado)** — 1 registro **CNAME**:

| Tipo | Nombre | Valor |
|------|--------|-------|
| CNAME | `www` | `marvinzzvla.github.io` |

### En GitHub (solo una vez)

1. **Settings → Pages → Custom domain** → escribe `resorias.com` y guarda.
2. Espera la verificación DNS (puede tardar hasta 24 h).
3. Activa **Enforce HTTPS** cuando GitHub lo permita.
4. **Source** debe ser **GitHub Actions**.

© Resoria — Easy Restaurant & Mi Inventario
