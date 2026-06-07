# CSS posiblemente muerto

Fecha: 2026-06-07

## Alcance

Se analizaron clases definidas en CSS activos y se compararon contra `index.html`.

CSS activos considerados:

- `css/bootstrap.css`
- `css/style.css`
- `css/responsive.css`
- `css/font-awesome.css`
- `css/flaticon.css`
- `css/animate.css`
- `css/jquery-ui.css`
- `css/owl.css`
- `css/jquery.fancybox.css`
- `plugins/revolution/css/settings.css`
- `plugins/revolution/css/layers.css`
- `plugins/revolution/css/navigation.css`

No se modifico ningun CSS.

## Resumen

- Clases CSS detectadas: 2906 aprox.
- Clases encontradas en `index.html`: 126 aprox.
- Clases no encontradas directamente en `index.html`: 2780 aprox.

Este numero es alto porque el proyecto conserva Bootstrap, FontAwesome, Flaticon, Revolution Slider y CSS de template completo.

## Clases CSS definidas pero no encontradas en index.html

Muestra representativa:

- `about-section`
- `about-section-two`
- `accordion-box`
- `achivements-logos`
- `approach-section`
- `author-box`
- `blog-grid-section`
- `blog-single`
- `call-to-action`
- `cart-box`
- `case-section`
- `choose-section`
- `clients-section`
- `contact-tabs`
- `counter-section`
- `gallery-section`
- `gallery-widget`
- `google-map`
- `masonry-items-container`
- `news-section`
- `page-title`
- `portfolio`
- `project-carousel`
- `project-section`
- `project-tab`
- `sidebar-page-container`
- `sponsors-carousel`
- `team-section`
- `testimonial-section`

## Selectores posiblemente heredados del template

Estos grupos parecen pertenecer a paginas/componentes del template que no estan presentes en `index.html`:

- About pages: `about-section`, `about-section-two`
- Blog/news: `blog-*`, `news-*`
- Portfolio/projects: `project-*`, `portfolio-*`, `gallery-*`
- Shop/cart/product: `shop`, `cart-box`, `product-*`
- Team/testimonials: `team-*`, `testimonial-*`
- Sidebar/page title: `sidebar-*`, `page-title`
- Counters: `count-box`, `counter-section`
- Maps: `google-map`, `map-section`
- Tabs/accordion: `tabs-*`, `accordion-box`
- Carousel/sponsors: `owl-*`, `sponsors-carousel`, `project-carousel`

## Selectores que conviene revisar manualmente

No mover ni borrar automaticamente mientras sigan importados/cargados:

- Bootstrap grid/utilidades: `col-*`, `row`, `clearfix`, `btn-*`, `navbar-*`
- FontAwesome: `fa-*`
- Flaticon: `flaticon-*`
- Revolution Slider: `tp-*`, `rev-*`, `uranus`, `ares`, clases de captions
- jQuery UI: `ui-*`
- Fancybox: `fancybox-*`
- Owl Carousel: `owl-*`
- Animate/WOW: `animated`, `bounce*`, `fade*`, etc.

## Recomendacion

La limpieza real de CSS muerto requiere primero decidir si se van a quitar del HTML/CSS las librerias aparentemente no usadas:

- jQuery UI
- Fancybox
- Owl Carousel
- WOW/Animate

Mientras esas librerias sigan cargadas o importadas, sus CSS deben permanecer.

