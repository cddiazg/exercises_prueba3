Flexbox y Grid: Todo lo que necesitas saber para tu examen de HTML y CSS
Flexbox (Flexible Box Layout)
Conceptos básicos
Modelo de diseño unidimensional (trabaja en una sola dimensión a la vez: fila o columna)

Contenedor flex (flex container) e ítems flex (flex items)

Eje principal (main axis) y eje transversal (cross axis)

Propiedades del contenedor flex
css
.container {
  display: flex; /* o inline-flex */
  flex-direction: row | row-reverse | column | column-reverse;
  flex-wrap: nowrap | wrap | wrap-reverse;
  flex-flow: <flex-direction> <flex-wrap>; /* shorthand */
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
  align-items: stretch | flex-start | flex-end | center | baseline;
  align-content: stretch | flex-start | flex-end | center | space-between | space-around;
}
Propiedades de los ítems flex
css
.item {
  order: <integer>; /* orden de visualización */
  flex-grow: <number>; /* capacidad de crecimiento */
  flex-shrink: <number>; /* capacidad de reducción */
  flex-basis: <length> | auto; /* tamaño base */
  flex: none | [ <flex-grow> <flex-shrink>? || <flex-basis> ]; /* shorthand */
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
Ejemplo práctico
html
<div class="flex-container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>

<style>
.flex-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 200px;
  background: lightblue;
}
.item {
  width: 50px;
  height: 50px;
  background: tomato;
}
</style>
CSS Grid Layout
Conceptos básicos
Modelo de diseño bidimensional (filas y columnas simultáneamente)

Contenedor grid (grid container) e ítems grid (grid items)

Líneas grid, celdas, áreas y tracks (pistas)

Propiedades del contenedor grid
css
.container {
  display: grid; /* o inline-grid */
  grid-template-columns: <track-size> ... | <line-name> <track-size> ...;
  grid-template-rows: <track-size> ... | <line-name> <track-size> ...;
  grid-template-areas: "<grid-area-name> ..." ...;
  grid-gap: <grid-row-gap> <grid-column-gap>; /* ahora gap en especificación actual */
  justify-items: start | end | center | stretch;
  align-items: start | end | center | stretch;
  justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
  align-content: start | end | center | stretch | space-around | space-between | space-evenly;
  grid-auto-columns: <track-size> ...;
  grid-auto-rows: <track-size> ...;
  grid-auto-flow: row | column | row dense | column dense;
}
Propiedades de los ítems grid
css
.item {
  grid-column-start: <number> | <name> | span <number> | span <name> | auto;
  grid-column-end: <number> | <name> | span <number> | span <name> | auto;
  grid-row-start: <number> | <name> | span <number> | span <name> | auto;
  grid-row-end: <number> | <name> | span <number> | span <name> | auto;
  grid-column: <start-line> / <end-line> | <start-line> / span <value>;
  grid-row: <start-line> / <end-line> | <start-line> / span <value>;
  grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
  justify-self: start | end | center | stretch;
  align-self: start | end | center | stretch;
}
Ejemplo práctico
html
<div class="grid-container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main Content</div>
  <div class="footer">Footer</div>
</div>

<style>
.grid-container {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-rows: 80px 1fr 80px;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  height: 100vh;
  gap: 10px;
}
.header { grid-area: header; background: lightblue; }
.sidebar { grid-area: sidebar; background: lightgreen; }
.main { grid-area: main; background: lightyellow; }
.footer { grid-area: footer; background: lightpink; }
</style>
Diferencias clave entre Flexbox y Grid
Característica	Flexbox	Grid
Dimensión	Unidimensional (fila o columna)	Bidimensional (filas y columnas)
Alineación	Excelente para alinear ítems	También permite alineación pero más enfocado en estructura general
Ordenación	Fácil reordenamiento con order	También posible pero menos común
Uso ideal	Componentes pequeños y alineación	Diseños de página completos
Control de espacio	Distribución a lo largo de un eje	Control preciso en ambos ejes
Preguntas comunes en exámenes
¿Cuándo usarías Flexbox en lugar de Grid?

Para diseños unidimensionales (una fila o una columna)

Para alinear elementos dentro de un contenedor

Para distribuir espacio entre elementos en una sola dirección

¿Cuándo usarías Grid en lugar de Flexbox?

Para diseños bidimensionales complejos

Cuando necesitas control preciso sobre filas y columnas simultáneamente

Para crear layouts con áreas nombradas

¿Cómo centras un elemento tanto vertical como horizontalmente con Flexbox?

css
.container {
  display: flex;
  justify-content: center; /* centrado horizontal */
  align-items: center; /* centrado vertical */
}
¿Cómo defines un área en CSS Grid?

css
.container {
  display: grid;
  grid-template-areas: "header header"
                       "sidebar main"
                       "footer footer";
}
.header { grid-area: header; }
¿Qué hace flex: 1?

Es equivalente a flex: 1 1 0

Permite que el elemento crezca y se reduzca según el espacio disponible

Establece la base flexible en 0

Consejos para el examen
Practica creando layouts comunes (navbar, card grids, formularios) con ambos métodos

Entiende cómo funcionan juntos Flexbox y Grid (puedes usar Flexbox dentro de un ítem Grid y viceversa)

Memoriza las propiedades principales y sus valores más comunes

Presta atención a la compatibilidad con navegadores (aunque ambos son ampliamente soportados en versiones modernas)

¡Buena suerte en tu examen!

New chat
