# Duplicados

Fecha: 2026-06-07

## Alcance

Se buscaron duplicados por hash en el estado actual del filesystem. La carpeta `_unused` existe, pero actualmente esta vacia.

## Logos duplicados

No se encontraron logos duplicados por hash en el arbol activo.

Logos activos que conviene conservar:

- `images/et-logo.png`
- `images/et-logo-white.png`

No tocar: ambos estan referenciados por `index.html`.

## Imagenes duplicadas

No se encontraron imagenes duplicadas por hash en el arbol activo actual.

Imagenes principales que conviene conservar:

- `images/favicon.png`
- `images/main-slider/hero_img.png`
- `images/icons/preloader.GIF`
- `images/icons/icon-cross.png`
- `images/icons/icon-select.png`
- `images/fancybox/*` mientras Fancybox siga cargado/importado
- `css/images/ui-icons_*.png` mientras jQuery UI siga importado
- `plugins/revolution/assets/*.png` usados por CSS de Revolution

## Fuentes duplicadas

Se encontraron duplicados exactos de Revicons:

- `fonts/revicons90c6.eot`
- `plugins/revolution/fonts/revicons/revicons.eot`

- `fonts/revicons90c6.ttf`
- `plugins/revolution/fonts/revicons/revicons.ttf`

- `fonts/revicons90c6.woff`
- `plugins/revolution/fonts/revicons/revicons.woff`

Recomendacion:

- Conservar `plugins/revolution/fonts/revicons/revicons.*`, porque `plugins/revolution/css/settings.css` apunta a esa ubicacion.
- Revisar manualmente `fonts/revicons90c6.*` antes de moverlos, porque son parte del ecosistema de Revolution y la regla indica no tocar Revolution si esta referenciado.

## Iconos duplicados

No se encontraron iconos duplicados por hash en el arbol activo actual.

Iconos/fuentes que conviene conservar:

- `fonts/fontawesome-webfont.*`
- `fonts/FontAwesome.otf`
- `fonts/flaticon.*`
- `fonts/glyphicons-halflings-regular.*`
- `plugins/revolution/fonts/revicons/revicons.*`

## Recomendacion general

No hacer limpieza automatica adicional de duplicados sin una pasada manual. Los duplicados detectados estan en fuentes asociadas a librerias protegidas por las reglas del proyecto.

