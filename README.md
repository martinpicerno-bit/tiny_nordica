# Tiny Granero — Landing page

Landing estática construida en **Astro** (SSG) con despliegue en **Cloudflare Pages**.

## Estructura

```
/
├─ astro.config.mjs          # Configuración Astro
├─ package.json
├─ tsconfig.json
├─ public/
│  ├─ images/                # hero.jpg, space-1/2/3.jpg, og-image.jpg
│  ├─ logo.png               # → agregar
│  ├─ favicon.png            # → agregar
│  ├─ _headers               # Security headers Cloudflare
│  └─ _redirects             # Redirects Cloudflare
└─ src/
   ├─ data/site.ts           # ← VARIABLES EDITABLES (URLs, precios, flags)
   ├─ content/landing.ts     # ← TEXTOS EDITABLES (copias, FAQ, listas)
   ├─ layouts/BaseLayout.astro
   ├─ components/            # Un componente por sección
   ├─ styles/
   │  ├─ tokens.css          # Paleta, tipografía, espaciado
   │  └─ global.css
   └─ pages/index.astro      # Página principal
```

## Desarrollo local

```bash
npm install
npm run dev
```

## Producción

```bash
npm run build   # genera /dist
```

## Despliegue en Cloudflare Pages

1. Conectar el repositorio en el panel de Cloudflare Pages.
2. Build command: `npm run build`
3. Build output directory: `dist`
4. Node.js version: 18 o superior.

Los archivos `_headers` y `_redirects` en `/public` se aplican automáticamente.

## Variables a completar antes de producción

Editar `src/data/site.ts`:

| Variable | Estado |
|---|---|
| `WHATSAPP_URL` | ✅ Configurado |
| `AIRBNB_URL` | ✅ Configurado |
| `INSTAGRAM_URL` | ⚠️ Pendiente |
| `POLITICA_PRIVACIDAD_URL` | ⚠️ Pendiente |
| `siteUrl` | ⚠️ Ajustar al dominio real |
| `META_PIXEL_ID` | ⚠️ Pendiente (opcional) |

## Imágenes a completar

| Archivo | Estado |
|---|---|
| `public/images/hero.jpg` | ✅ Provisto |
| `public/images/space-1.jpg` | ✅ Provisto |
| `public/images/space-2.jpg` | ✅ Provisto |
| `public/images/space-3.jpg` | ✅ Provisto |
| `public/images/og-image.jpg` | ⚠️ Pendiente (puede usar hero.jpg) |
| `public/logo.png` | ⚠️ Pendiente |
| `public/favicon.png` | ⚠️ Pendiente |

## Cambios frecuentes

- **Precios** → `src/data/site.ts` → `precio_semana` / `precio_finde`
- **Textos y FAQ** → `src/content/landing.ts`
- **Mostrar/ocultar precios** → `PRECIO_VISIBLE_EN_LANDING: true/false`
- **Agregar experiencias extras** → `EXTRAS.items` en `landing.ts`
- **Links** → `src/data/site.ts`
