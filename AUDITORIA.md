# Auditoria de archivos no utilizados

Fecha: 2026-06-07

Alcance: sitio estatico HTML/CSS/JS. La unica pagina considerada como entrada es `index.html`.

Metodo:
- Se tomaron como activos los `href` y `src` reales de `index.html`, excluyendo HTML comentado.
- Se siguieron dependencias internas de CSS mediante `@import` y `url(...)`.
- No se considero como activo lo que aparece solo en comentarios, archivos fuente no cargados o demos del template.
- La clasificacion es conservadora: si un archivo esta cargado por `index.html`, aunque parezca innecesario para el markup actual, queda en "Revisar manualmente" o "No tocar".

## Resumen ejecutivo

- `index.html` carga directamente 6 CSS principales y 21 JS locales.
- `css/style.css` importa 6 CSS adicionales: `font-awesome`, `flaticon`, `animate`, `jquery-ui`, `owl` y `jquery.fancybox`.
- La pagina actual solo muestra uso claro de Revolution Slider (`#rev_slider_one`).
- No se encontraron en `index.html` clases/estructuras para Owl Carousel, Fancybox, MixItUp, Isotope, Google Maps, contadores con Appear, tabs/accordions del template ni animaciones `.wow`.
- Hay una gran cantidad de assets heredados del template, especialmente SVGs de Revolution Slider, PHP de integraciones sociales y archivos fuente no minificados.

## 1. Archivos no referenciados desde index.html

### Seguro mover a `_unused`

Estos archivos/carpetas no estan enlazados por `index.html` ni por los CSS activos:

- `estructura.txt`
- `plugins/revolution/php/`
- `plugins/revolution/js/source/`
- `plugins/revolution/js/extensions/source/`
- `plugins/revolution/js/jquery.themepunch.enablelog.js`
- `plugins/revolution/js/tp-color-picker.min.js`
- `plugins/revolution/css/tp-color-picker.css`
- `plugins/revolution/css/settings-source.css`
- `plugins/revolution/images/tpcolorpicker/`
- `plugins/revolution/fonts/pe-icon-7-stroke/`
- `plugins/revolution/fonts/font-awesome/`
- `css/assets/*.psd`

Tambien aparecen como no referenciados los `index.php` vacios dentro de `plugins/revolution/`. Si el sitio se sirve como estatico puro, se pueden mover; si se sube a un hosting PHP antiguo que usa esos archivos para evitar listado de directorios, revisar antes.

### Revisar manualmente

Archivos cargados directa o indirectamente pero sin componentes visibles en el HTML actual:

- `js/jquery-ui.js`
- `js/jquery.fancybox.pack.js`
- `js/jquery.fancybox-media.js`
- `js/owl.js`
- `js/appear.js`
- `js/wow.js`
- `css/jquery-ui.css`
- `css/jquery.fancybox.css`
- `css/owl.css`
- `css/animate.css`

Motivo: estan cargados o importados, pero `index.html` no contiene `.custom-select-box`, `.lightbox-image`, carruseles Owl, `.count-box` ni `.wow`.

### No tocar

Base activa del sitio:

- `index.html`
- `css/bootstrap.css`
- `css/style.css`
- `css/responsive.css`
- `css/font-awesome.css`
- `css/flaticon.css`
- `plugins/revolution/css/settings.css`
- `plugins/revolution/css/layers.css`
- `plugins/revolution/css/navigation.css`
- `js/jquery.js`
- `js/bootstrap.min.js`
- `js/main-slider-script.js`
- `js/script.js`
- `plugins/revolution/js/jquery.themepunch.revolution.min.js`
- `plugins/revolution/js/jquery.themepunch.tools.min.js`
- `plugins/revolution/js/extensions/*.min.js`
- Fuentes usadas por Bootstrap, Font Awesome, Flaticon y Revicons.

## 2. Imagenes no utilizadas

### Seguro mover a `_unused`

Imagenes propias no referenciadas por `index.html` ni por CSS activos:

- `images/ET.png`
- `images/et-logo.svg`
- `images/et-logo-white.svg`
- `images/footer-logo.png`
- `images/logo.png`
- `images/logo-2.png`
- `images/logo-small.png`
- `images/icons/icon-toggle.png`
- `images/icons/map-marker.png`
- `images/icons/submenu-icon.png`
- `images/icons/tick.png`
- `images/icons/usa.jpg`
- `images/main-slider/image-1-a.jpg`
- `images/main-slider/image-1-b.jpg`
- `images/main-slider/image-1-c.jpg`
- `images/main-slider/image-1-d.jpg`
- `images/main-slider/image-2-a.jpg`
- `images/main-slider/image-2-b.jpg`
- `images/main-slider/image-2-c.jpg`
- `images/main-slider/image-3-a.jpg`
- `images/main-slider/image-3-b.jpg`
- `images/main-slider/image-3-c.jpg`
- `images/main-slider/image-4-a.jpg`
- `images/main-slider/image-4-b.jpg`
- `images/main-slider/image-4-c.jpg`

Assets masivos de plugin no usados por la configuracion actual:

- `plugins/revolution/assets/svg/` completo: 1228 SVG aprox. sin referencia activa.
- `plugins/revolution/images/tpcolorpicker/` completo: 11 imagenes aprox.
- `css/assets/` completo: 41 imagenes aprox. no referenciadas por los CSS activos actuales.

### Revisar manualmente

Estas imagenes son cargadas por CSS importados que parecen no tener componentes activos en `index.html`:

- `images/fancybox/`
- `css/images/ui-icons_444444_256x240.png`
- `css/images/ui-icons_555555_256x240.png`

Si se eliminan Fancybox y jQuery UI del HTML/CSS, estas pasan a "Seguro mover".

### No tocar

Imagenes activas o dependencias directas:

- `images/favicon.png`
- `images/et-logo.png`
- `images/et-logo-white.png`
- `images/main-slider/hero_img.png`
- `images/icons/preloader.GIF`
- `images/icons/icon-cross.png`
- `images/icons/icon-select.png`
- `plugins/revolution/assets/coloredbg.png`
- `plugins/revolution/assets/gridtile.png`
- `plugins/revolution/assets/gridtile_3x3.png`
- `plugins/revolution/assets/gridtile_3x3_white.png`
- `plugins/revolution/assets/gridtile_white.png`
- `plugins/revolution/assets/loader.gif`

## 3. CSS no utilizados

### Seguro mover a `_unused`

- `css/hover.css`
- `plugins/revolution/css/settings-source.css`
- `plugins/revolution/css/tp-color-picker.css`
- `plugins/revolution/css/navigation-skins/ares.css`
- `plugins/revolution/css/navigation-skins/custom.css`
- `plugins/revolution/css/navigation-skins/dione.css`
- `plugins/revolution/css/navigation-skins/erinyen.css`
- `plugins/revolution/css/navigation-skins/gyges.css`
- `plugins/revolution/css/navigation-skins/hades.css`
- `plugins/revolution/css/navigation-skins/hebe.css`
- `plugins/revolution/css/navigation-skins/hephaistos.css`
- `plugins/revolution/css/navigation-skins/hermes.css`
- `plugins/revolution/css/navigation-skins/hesperiden.css`
- `plugins/revolution/css/navigation-skins/metis.css`
- `plugins/revolution/css/navigation-skins/persephone.css`
- `plugins/revolution/css/navigation-skins/uranus.css`
- `plugins/revolution/css/navigation-skins/zeus.css`
- `plugins/revolution/fonts/font-awesome/css/font-awesome.css`
- `plugins/revolution/fonts/font-awesome/css/font-awesome.min.css`
- `plugins/revolution/fonts/pe-icon-7-stroke/css/helper.css`
- `plugins/revolution/fonts/pe-icon-7-stroke/css/pe-icon-7-stroke.css`

Nota: aunque `main-slider-script.js` usa `style:"uranus"` para las flechas, el CSS de skins separado no esta enlazado. La navegacion activa depende de `plugins/revolution/css/navigation.css`.

### Revisar manualmente

- `css/animate.css`
- `css/jquery-ui.css`
- `css/jquery.fancybox.css`
- `css/owl.css`

Estos estan importados por `css/style.css`, pero no hay markup actual que los necesite.

### No tocar

- `css/bootstrap.css`
- `css/style.css`
- `css/responsive.css`
- `css/font-awesome.css`
- `css/flaticon.css`
- `plugins/revolution/css/settings.css`
- `plugins/revolution/css/layers.css`
- `plugins/revolution/css/navigation.css`

## 4. JS no utilizados

### Seguro mover a `_unused`

No estan cargados por `index.html`:

- `js/isotope.js`
- `js/jquery.easing.min.js`
- `js/map-script.js`
- `js/mixitup.js`
- `plugins/revolution/js/jquery.themepunch.enablelog.js`
- `plugins/revolution/js/tp-color-picker.min.js`
- `plugins/revolution/js/source/jquery.themepunch.enablelog.js`
- `plugins/revolution/js/source/jquery.themepunch.revolution.js`
- `plugins/revolution/js/source/jquery.themepunch.tools.min.js`
- `plugins/revolution/js/source/tp-color-picker.js`
- `plugins/revolution/js/extensions/source/revolution.extension.actions.js`
- `plugins/revolution/js/extensions/source/revolution.extension.carousel.js`
- `plugins/revolution/js/extensions/source/revolution.extension.kenburn.js`
- `plugins/revolution/js/extensions/source/revolution.extension.layeranimation.js`
- `plugins/revolution/js/extensions/source/revolution.extension.migration.js`
- `plugins/revolution/js/extensions/source/revolution.extension.navigation.js`
- `plugins/revolution/js/extensions/source/revolution.extension.parallax.js`
- `plugins/revolution/js/extensions/source/revolution.extension.slideanims.js`
- `plugins/revolution/js/extensions/source/revolution.extension.video.js`

### Revisar manualmente

Estan cargados por `index.html`, pero no hay markup actual que active su uso:

- `js/jquery-ui.js`
- `js/jquery.fancybox.pack.js`
- `js/jquery.fancybox-media.js`
- `js/owl.js`
- `js/appear.js`
- `js/wow.js`

`js/script.js` contiene inicializadores para estos plugins, pero casi todos estan protegidos por checks de existencia de clases que hoy no aparecen en `index.html`.

### No tocar

- `js/jquery.js`
- `js/bootstrap.min.js`
- `js/main-slider-script.js`
- `js/script.js`
- `plugins/revolution/js/jquery.themepunch.revolution.min.js`
- `plugins/revolution/js/jquery.themepunch.tools.min.js`
- `plugins/revolution/js/extensions/revolution.extension.actions.min.js`
- `plugins/revolution/js/extensions/revolution.extension.carousel.min.js`
- `plugins/revolution/js/extensions/revolution.extension.kenburn.min.js`
- `plugins/revolution/js/extensions/revolution.extension.layeranimation.min.js`
- `plugins/revolution/js/extensions/revolution.extension.migration.min.js`
- `plugins/revolution/js/extensions/revolution.extension.navigation.min.js`
- `plugins/revolution/js/extensions/revolution.extension.parallax.min.js`
- `plugins/revolution/js/extensions/revolution.extension.slideanims.min.js`
- `plugins/revolution/js/extensions/revolution.extension.video.min.js`

## 5. Plugins posiblemente no utilizados

### Seguro mover a `_unused`

Plugins/partes de plugin no cargadas:

- MixItUp: `js/mixitup.js`
- Isotope/Masonry: `js/isotope.js`
- Google Maps custom script: `js/map-script.js`
- jQuery Easing: `js/jquery.easing.min.js`
- Revolution color picker: `plugins/revolution/js/tp-color-picker.min.js`, `plugins/revolution/css/tp-color-picker.css`, `plugins/revolution/images/tpcolorpicker/`
- Revolution PHP social/video connectors: `plugins/revolution/php/`
- Revolution source files no minificados: `plugins/revolution/js/source/`, `plugins/revolution/js/extensions/source/`
- Revolution icon SVG library: `plugins/revolution/assets/svg/`

### Revisar manualmente

Cargados, pero sin evidencia de uso en el HTML actual:

- Owl Carousel: `js/owl.js`, `css/owl.css`
- Fancybox: `js/jquery.fancybox.pack.js`, `js/jquery.fancybox-media.js`, `css/jquery.fancybox.css`
- jQuery UI: `js/jquery-ui.js`, `css/jquery-ui.css`
- WOW/Animate: `js/wow.js`, `css/animate.css`
- Appear/counting: `js/appear.js`

### No tocar

Usados por la pagina actual:

- jQuery
- Bootstrap
- Font Awesome
- Flaticon
- Revolution Slider runtime

## Observaciones

- Hay referencias comentadas en `index.html` a `css/color-themes/blue-theme.css`, `js/respond.js` y `html5shiv` por condicional IE. No se encontraron como activos.
- `css/style.css` referencia imagenes que no existen en disco, como `images/background/1.jpg`, `images/resource/bg-layer.jpg` y `images/resource/consult-bg.jpg`. No son "unused"; son referencias rotas o heredadas del template.
- Antes de mover archivos cargados directamente por `index.html`, conviene limpiar las etiquetas `<script>`/`<link>` correspondientes para evitar 404 en consola.
