# Quilino Reyes · Documentación del Proyecto

## Descripción General

**Quilino Reyes** es una aplicación web desarrollada con [Nuxt.js](https://nuxt.com/) que ha evolucionado de una simple landing page a un sitio completo de catálogo de moda, con enfoque en productos como corbatas y colecciones de moda para hombre y mujer. El proyecto utiliza la arquitectura **JAMstack** para lograr un sitio rápido, seguro y fácilmente escalable.

---

## Motivación del Cambio

El proyecto comenzó como una landing page estática para presentar la marca y su primera colección. Con el crecimiento de la marca y la necesidad de mostrar más productos y colecciones, se migró a una arquitectura JAMstack usando Nuxt.js, permitiendo:

- Mejor organización y escalabilidad del código.
- Navegación dinámica entre secciones y productos.
- Mejor experiencia de usuario y rendimiento.
- Facilidad para añadir nuevas colecciones y funcionalidades.

---

## Tecnologías Utilizadas

- **Nuxt.js**: Framework basado en Vue.js para aplicaciones universales y JAMstack.
- **Vue.js**: Framework progresivo para la construcción de interfaces de usuario.
- **Arquitectura JAMstack**: Separación del frontend y backend, generación de sitios estáticos y despliegue en CDN.
- **CSS personalizado**: Para el diseño responsive y visual de la marca.

---

## Estructura del Proyecto

```
/layouts
  default.vue         # Layout principal con header y footer responsive
/pages
  index.vue           # Página de inicio con presentación y navegación
  /modahombre         # Sección de moda hombre
  /modamujer          # Sección de moda mujer
  /corbatashombre     # Catálogo de corbatas para hombre
/components
  ProductList.vue     # Componente reutilizable para mostrar productos
/public
  /corbatas/data.js   # Datos de productos (corbatas)
  /logo-bg.jpg        # Recursos estáticos
```

---

## Funcionalidades Principales

- **Header Responsive**: Menú adaptable con navegación entre secciones, menú hamburguesa en móviles y cierre automático al navegar.
- **Catálogo Dinámico**: Listado de productos por temporada, con pestañas y visualización responsive.
- **Presentación de Marca**: Página principal con historia, imagen destacada y botones de acceso rápido a las colecciones.
- **Diseño Responsive**: Adaptación total a dispositivos móviles y escritorio.
- **Separación de datos y vistas**: Los productos se gestionan desde archivos de datos, facilitando la actualización y escalabilidad.

---

## Instalación y Puesta en Marcha

Asegúrate de instalar las dependencias:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

### Servidor de Desarrollo

Inicia el servidor de desarrollo en `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm dev

# yarn
yarn dev

# bun
bun run dev
```

### Producción

Construye la aplicación para producción:

```bash
# npm
npm run build

# pnpm
pnpm build

# yarn
yarn build

# bun
bun run build
```

Previsualiza la build de producción localmente:

```bash
# npm
npm run preview

# pnpm
pnpm preview

# yarn
yarn preview

# bun
bun run preview
```

Consulta la [documentación de despliegue](https://nuxt.com/docs/getting-started/deployment) para más información.

---

## Consideraciones

- El proyecto está pensado para despliegue estático (JAMstack), por lo que puede ser publicado fácilmente en servicios como Vercel, Netlify o GitHub Pages.
- La estructura modular permite añadir nuevas colecciones o productos simplemente agregando datos y componentes.

---

## Créditos

Desarrollado por Quilino Reyes.  
Para dudas o mejoras, contacta al equipo de desarrollo.
