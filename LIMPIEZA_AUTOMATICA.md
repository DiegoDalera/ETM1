# Limpieza automatica conservadora

Fecha: 2026-06-07

## Alcance

Se analizo el proyecto como sitio estatico con una unica entrada funcional: `index.html`.

No se modificaron:

- `index.html`
- CSS existentes
- JS existentes
- Bootstrap
- jQuery
- Revolution Slider referenciado
- FontAwesome
- Flaticon
- Logos actuales usados por `index.html`

## Resultado de limpieza

En esta ejecucion no se movieron archivos nuevos a `_unused`.

Motivo: el arbol activo ya esta reducido y los unicos candidatos no referenciados directamente quedaron protegidos por las reglas o por precaucion.

## Archivos movidos

Ninguno en esta ejecucion.

## Carpetas movidas

Ninguna en esta ejecucion.

## Archivos/carpetas no movidos por precaucion

Estos archivos aparecen como no referenciados en el grafo activo, pero no se movieron:

- `fonts/FontAwesome.otf`
- `fonts/revicons90c6.eot`
- `fonts/revicons90c6.svg`
- `fonts/revicons90c6.ttf`
- `fonts/revicons90c6.woff`
- `plugins/revolution/index.php`
- `plugins/revolution/assets/index.php`
- `plugins/revolution/css/index.php`
- `plugins/revolution/fonts/index.php`
- `plugins/revolution/fonts/revicons/index.php`
- `plugins/revolution/js/index.php`
- `plugins/revolution/js/extensions/index.php`

Razones:

- `fonts/FontAwesome.otf` pertenece a FontAwesome, que esta protegido por la regla "no tocar".
- `fonts/revicons90c6.*` son duplicados de Revicons, pero Revicons pertenece al ecosistema de Revolution Slider.
- Los `index.php` vacios dentro de `plugins/revolution/` pueden ser archivos defensivos para evitar listado de directorios en hostings PHP antiguos.

## Riesgos detectados

- La carpeta `_unused` existe pero actualmente no contiene archivos en el filesystem.
- Git registra muchos archivos dentro de `_unused` como eliminados. No se restauraron ni se modifico Git porque no fue solicitado.
- `css/style.css` importa librerias que parecen no tener componentes activos en `index.html`: `animate.css`, `jquery-ui.css`, `owl.css`, `jquery.fancybox.css`.
- `index.html` carga JS que no parece activarse con el markup actual: `jquery-ui.js`, `jquery.fancybox*.js`, `owl.js`, `appear.js`, `wow.js`.
- No conviene mover esos CSS/JS sin antes limpiar referencias en HTML/CSS, cosa que estaba prohibida en esta tarea.

## Verificacion conservadora

Se verifico que no falten archivos principales referenciados por:

- `index.html`
- `css/style.css`
- `css/responsive.css`
- `js/script.js`
- `js/main-slider-script.js`
- CSS activos importados desde `style.css`

