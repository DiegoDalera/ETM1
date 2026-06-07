# Documentacion del proyecto

Fecha: 2026-06-07

## Descripcion

Sitio estatico HTML/CSS/JS para ET Consultores. La unica pagina funcional considerada es `index.html`.

El sitio esta basado en un template y conserva dependencias de Bootstrap, FontAwesome, Flaticon y Revolution Slider.

## Estructura actual

```text
.
├── index.html
├── AUDITORIA.md
├── LIMPIEZA_AUTOMATICA.md
├── DUPLICADOS.md
├── CSS_MUERTO.md
├── JS_MUERTO.md
├── DOCUMENTACION_PROYECTO.md
├── css/
├── fonts/
├── images/
├── js/
├── plugins/
│   └── revolution/
└── _unused/
```

Conteo aproximado fuera de `.git`:

- `css/`: 11 archivos activos
- `fonts/`: 19 archivos activos
- `images/`: 13 archivos activos
- `js/`: 10 archivos activos
- `plugins/`: 33 archivos activos
- `_unused/`: carpeta presente, actualmente vacia en filesystem

## Archivo principal

- `index.html`

Contiene:

- Header y navegacion de una pagina.
- Slider principal Revolution.
- Secciones: inicio, quienes somos, experiencia, servicios, metodologia y contacto.
- Footer con logo blanco.
- CSS inline de branding.
- Scripts del template al final del documento.

## CSS principales

No tocar:

- `css/bootstrap.css`
- `css/style.css`
- `css/responsive.css`
- `css/font-awesome.css`
- `css/flaticon.css`
- `plugins/revolution/css/settings.css`
- `plugins/revolution/css/layers.css`
- `plugins/revolution/css/navigation.css`

CSS cargados/importados pero a revisar en una tarea separada:

- `css/animate.css`
- `css/jquery-ui.css`
- `css/owl.css`
- `css/jquery.fancybox.css`

## JS principales

No tocar:

- `js/jquery.js`
- `js/bootstrap.min.js`
- `js/script.js`
- `js/main-slider-script.js`
- `plugins/revolution/js/jquery.themepunch.revolution.min.js`
- `plugins/revolution/js/jquery.themepunch.tools.min.js`
- `plugins/revolution/js/extensions/*.min.js`

JS cargados pero posiblemente no usados por el markup actual:

- `js/jquery-ui.js`
- `js/jquery.fancybox.pack.js`
- `js/jquery.fancybox-media.js`
- `js/owl.js`
- `js/appear.js`
- `js/wow.js`

## Imagenes principales

No tocar:

- `images/favicon.png`
- `images/et-logo.png`
- `images/et-logo-white.png`
- `images/main-slider/hero_img.png`
- `images/icons/preloader.GIF`
- `images/icons/icon-cross.png`
- `images/icons/icon-select.png`
- `plugins/revolution/assets/*.png`

## Plugins utilizados

Utilizados claramente:

- jQuery
- Bootstrap
- FontAwesome
- Flaticon
- Revolution Slider

Cargados pero posiblemente sin uso activo:

- jQuery UI
- Fancybox
- Owl Carousel
- Appear
- WOW/Animate

## Que no conviene tocar

- `index.html`
- Logos PNG activos
- Bootstrap y su fuente Glyphicons
- jQuery
- FontAwesome y sus fuentes
- Flaticon y sus fuentes
- Revolution Slider runtime, CSS, extensiones y fuentes `plugins/revolution/fonts/revicons`
- `css/style.css` y `css/responsive.css` sin prueba visual posterior
- Los `index.php` vacios de `plugins/revolution/` si el hosting puede listar directorios

## Como probar el sitio despues de cambios

1. Abrir `index.html` en el navegador.
2. Confirmar que carguen los logos:
   - Header: `images/et-logo.png`
   - Footer: `images/et-logo-white.png`
3. Confirmar que el slider principal se vea y avance.
4. Revisar consola del navegador: no debe haber errores 404 de CSS, JS, fuentes o imagenes.
5. Probar navegacion interna:
   - Inicio
   - Quienes Somos
   - Servicios
   - Experiencia
   - Metodologia
   - Contacto
6. Probar responsive en mobile y desktop.
7. Confirmar que los iconos FontAwesome y Flaticon se vean correctamente.

## Nota sobre Git y `_unused`

El filesystem actual muestra `_unused` vacio, pero Git registra archivos de `_unused` como eliminados. No se hizo commit ni se restauraron archivos porque no fue solicitado.

