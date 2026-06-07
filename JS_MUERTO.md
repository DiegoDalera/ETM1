# JS posiblemente muerto

Fecha: 2026-06-07

## Alcance

Se revisaron los JS activos cargados por `index.html` y los inicializadores dentro de:

- `js/script.js`
- `js/main-slider-script.js`

No se modifico ningun JS.

## Funciones no llamadas

En `js/script.js` se detectaron estas funciones propias:

- `handlePreloader`: llamada desde `window.load`.
- `headerStyle`: llamada al iniciar y durante scroll.
- `enableMasonry`: llamada al iniciar y durante load.

No aparecen funciones propias claramente no llamadas dentro de `js/script.js`.

En `js/main-slider-script.js` no se detectaron funciones propias declaradas; es un inicializador de Revolution Slider.

## Plugins cargados pero aparentemente no usados

Estos plugins estan cargados por `index.html`, pero el markup actual no contiene las clases/estructuras que los activan:

- jQuery UI: `js/jquery-ui.js`
  - Buscado: `.custom-select-box`
  - Estado: no encontrado en `index.html`.

- Fancybox: `js/jquery.fancybox.pack.js`, `js/jquery.fancybox-media.js`
  - Buscado: `.lightbox-image`
  - Estado: no encontrado en `index.html`.

- Owl Carousel: `js/owl.js`
  - Buscado: `.sponsors-carousel`, `.two-item-carousel`, `.four-item-carousel`, `.single-item-carousel`, `.three-item-carousel`, `.project-carousel`
  - Estado: no encontrado en `index.html`.

- Appear/counting: `js/appear.js`
  - Buscado: `.count-box`
  - Estado: no encontrado en `index.html`.

- WOW: `js/wow.js`
  - Buscado: clases `.wow` en markup.
  - Estado: no encontrado como clase activa en `index.html`.

## Codigo heredado del template

`js/script.js` contiene inicializadores protegidos por checks de existencia. Si las clases no existen, no se ejecutan:

- Dropdowns de menu con `.dropdown`
- Select custom con `.custom-select-box`
- Carruseles Owl
- Masonry/Isotope con `.masonry-items-container`
- Contadores con `.count-box`
- Filtros con `.filter-list`
- Tabs y accordions
- Fancybox
- Validacion de formularios `.contact-page-form-*`
- WOW animations

Esto confirma que `script.js` es generico del template y contiene codigo para componentes no usados por esta unica pagina.

## Revolution Slider

`js/main-slider-script.js` inicializa:

- `#rev_slider_one`: existe en `index.html`.
- `#rev_slider_two`: no existe en `index.html`.

Recomendacion:

- No tocar Revolution Slider automaticamente porque `#rev_slider_one` esta activo y el plugin esta referenciado por `index.html`.
- El bloque de `#rev_slider_two` parece heredado, pero no debe modificarse bajo las reglas de esta tarea.

## Recomendacion

Antes de quitar JS aparentemente muerto, habria que permitir una tarea separada que edite `index.html` y retire scripts, seguida de prueba visual. En esta tarea eso estaba prohibido.

