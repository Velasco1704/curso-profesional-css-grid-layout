# Curso Profesional de CSS Grid Layout

## Cómo fue pensado CSS cuando se creó?

Tim Berners Lee creó WWW y HTML en 1991: (el tenía un hoja de estilos NO CSS, pero no quería compartirlo ya que pensaba que un feature así tenia que ser NATIVO) **1993**.

- Viola(navegador), tenía su propio lenguaje de estilos y queria convertirlo en un lenguaje estandara para la web. **1994**.
- NSCA Mosaic(navegador), tenía a Marc Andreessen como co-creador, les dijo a los desarrolladores que no había forma de trabajar con algo así(CSS). **-håkon wium lie**: sacó una propuesta para algo así **CHSS** .
- Se dió a la luz presentando dicha propuesta inicial. debatiendo si cualquier usuario pudiera manipular los estilos. 1995:
- **håkon y Bert Bos**: se unen y responder al 1er borrador en la conf de WWW en 1995.(algó que término siendo muy importante fue que sacarón la "H" y término siendo CSS).

-Se siguió debatiendo el control del usuario sobre los estílos, esta idea término siendo rechazada.

- **W3C**: saca una junta, ya que era de su interés. **1996**.
- **EL NACIMIENTO DE CSS**: La cual término naciendo por recomendación de W3C. **Primeros navegadores Compatibles**.
- Internet Explorer 3.
- NETSCAPE.
- OPERA **CSS 2**: nace en 1998, con correcciones con las limitaciones y el problema de los elementos **FLOTANTES**.

## Limitaciones de CSS y el problema de los elementos flotantes

**columnas falsas** es una técnica que hace una ilusión cuando una columna es más pequeña que otra se la rellena de un background de tipo imagen.

- Los primeros diseños de CSS eran una mezcla entre elementos flotantes y posicionados:

  - Haciendo que se tengan limitaciones de control.
  - Provocando que la información no se vea uniforme.

- Existía una frustración por la falta de columnas de altura completa:

  - Para solucionarlo se creó una técnica **de columnas falsas**.

- Se empieza hablar de Diseño Responsivo:
  - Ethan Marcotte: Técnica de diseño responsivo.

```css
@media screen and (max-width: 400px) {
  .figure,
  li#f-mycroft {
    margin-right: 3.317535545023696682%; /* 21px / 633px */
    width: 48.341232227488151658%; /* 306px / 633px */
  }
  li#f-watson,
  li#f-moriarty {
    margin-right: 0;
  }
}
```

- Se empieza a trabajar con elementos flotantes:
  - El problema está que solo funciona cuando se calcula con precisión el ancho y si el contenido tiene la misma altura.
  - La solución fue que se comenzó a trabajar con columnas a través de contenedores para cada una y no con elementos independientes.
  - También se comienza a usar display: table que también se pueden utilizar para elementos que no son elementos de tablas.
- Existen una gran cantidad de técnicas que son simplemente trucos:
  - Por ello CSS se ha visto difícil y frágil porque no había herramientas de diseño.

## Herramientas que nos han facilitado el camino

Post procesadores son herramientas que procesan el CSS y lo transforman en una nueva hoja de CSS que le permiten optimizar y automatizar los estilos para los navegadores actuales

- **Arquitecturas**
  - Es tener una regla general en CSS.
  - Usando sistema de clases como ser BEM.
- **Pre y Post procesadores**
  - Pre procesadores: Cambia la sintaxis de CSS permitiendo trabajar más rápido.
  - Post procesadores
- **Diseño de componentes**
  - Ej. Atomic Design.
  - Lo que se busca ya no es trabajar con páginas enteras sino con componentes.
- **Frameworks**
  - Muchos sitios iguales se deben a frameworks como Bootstrap y Foundation.
  - Nos permiten trabajar de una manera sencilla con los estilos.
- **Performance**
  - Es importante revisar cuanto va ser el costo en el navegador
- **Accesibilidad**
  - Actualmente se busca que todo tipo de personas puedan acceder a nuestros sitios web.
- **Evergreen Browsers**
  - Navegadores compatibles con nuevas características de la web.

## Técnicas de alineamiento antes de CSS Grid

### Margin collapsing

El **Margin collapsing** o colapso de márgenes es un fenómeno que ocurre en CSS cuando los márgenes verticales de dos elementos adyacentes se tocan, lo que provoca que se fusionen en un solo margen. Este efecto puede tener implicaciones en el diseño y el espaciado de los elementos en una página web.

### Técnicas de Margin

- Propiedades que necesitamos

  - margin-top
  - margin-right
  - margin-bottom
  - margin-left

### Técnica line-height

- **Text Align**
  - Nos permite alinear textos de forma horizontal
- **Vertical Align**
  - Nos permite alinear textos de forma vertical
- **Line Height**
  - Nos permite controlar los altos de los textos
- **Técnica Table Cell Propiedades que necesitamos**
  - display: table-cell
  - text-align
  - vertical-align

### Técnica positions Propiedades que necesitamos

- position: relative
- position: absolute
- top
- right
- bottom
- left
- transform: translate()

## Pros y Contras de Técnica de alineamiento antes de CSS Grid

### Margin

- **Ventajas**: El valor auto alinea horizontalmente cualquier elemento con cualquier ancho.
- **Desventajas**: Alinear verticalmente, ya que, en cada caso, deberán calcularse estos valores.

### line-height

- **Ventajas**: correcta alineación.
- **Desventajas**: si el texto ocupa más de una linea el elemento toma un alto más grande de lo necesario para los cálculos.

### table-cell

- **Ventajas**: La alineación vertical no esta condicionada por fuentes, tamaños de fuentes o alturas de linea.
- **Desventajas**: vertical-align sólo se aplica a elementos inline.

La mayor limitante de todas ellas es que contienen muchas propiedades físicas:

- margin-top
- padding-bottom
- border-right
- left

## Modos de escritura y ejes de alineamiento

- **horizontal-tb**: El contenido fluye horizontalmente de izquierda a derecha y verticalmente de arriba hacia abajo. El próximo renglón horizontal se posiciona debajo del renglón anterior.

- **vertical-rl**: El contenido fluye verticalmente de arriba hacia abajo y horizontalmente de derecha a izquierda. El próximo renglón vertical se posiciona a la izquierda del renglón anterior.

- **vertical-lr**: El contenido fluye verticalmente de arriba hacia abajo y horizontalmente de izquierda a derecha. El próximo renglón vertical se posiciona a la derecha del renglón anterior.

- **sideways-rl**: El contenido fluye verticalmente de arriba hacia abajo y todos los glifos, incluidos aquellos de los sistemas de escritura verticales, se colocan de lado hacia la derecha.

**sideways-lr**: El contenido fluye verticalmente de arriba hacia abajo y todos los glifos, incluidos aquellos de los sistemas de escritura verticales, se colocan de lado hacia la izquierda.

![image](https://static.platzi.com/media/user_upload/Screenshot_1adadadad-b90f01fe-89bb-4b93-a20d-9068740c6be1.jpg "image")

## Propiedades físicas y lógicas en CSS

### Propiedades físicas

- **Margin**: margin-top | Margin-left | Margin-right | Margin-bottom.
- **Padding**: padding-top | padding-left | padding-right | padding-bottom.
- **Border**: border-top | border-left | border-right | border-bottom.
- **Positions**: top | left | right | bottom.

### Propiedades Lógicas

- **Margin**: Margin-block-start | Margin-inline-start | Margin-inline-end | Margin-block-end.
- **Padding**: padding-block-start | padding-inline-start | padding-inline-end | padding-block-end.
- **Border**: border-block-start | border-inline-start | border-inline-end | border-block-end.
- **Positions**: inset-block-start | inset-inline-start | inset-inline-end | inset-block-end.

![image](https://static.platzi.com/media/user_upload/2021-02-23%20%2819%29-3b55dd2d-e982-4dd7-9eb7-051ea0ceb611.jpg "image")

## Técnicas de alineamiento con Flexbox

Las propiedades que tenemos que tener en cuenta para el alineamiento son estas 3:

- Display: Flex.
- Justify-content: Es para los elementos en su alineación horizontal.
- align-items: Es para alinear los elementos de forma vertical.

![image](https://static.platzi.com/media/user_upload/justify-content-cc6fe64c-293a-4887-b857-6b45a36db7ec.jpg)
![image](https://static.platzi.com/media/user_upload/align-items-be52d3c6-6a61-42ec-8586-2df719eb0b42.jpg)

## Grid y las relaciones padre e hijos inmediatos

CSS Grid se puede utilizar para lograr muchos diseños diferentes. También se destaca por permitir dividir una página en áreas o regiones principales, por definir la relación en términos de tamaño, posición y capas entre partes de un control construido a partir de primitivas HTML.

- Grid nos permite crear rejillas que tenga **filas** y **columnas**.

- En este momento se tiene una mayor complejidad en el diseño web.

- Siempre se tendrá un Contenedor (padre).

  - Los items (elementos hijos) serán los que estarán dentro de este contenedor.
    - Los hijos también pueden ser padres.

- Todos los padres tienen que tener.

```css
display: grid;
```

## Lines, tracks, cell, area, gutters, grid axis, grid row, grid column

- **Line** son las líneas divisorias que componen la estructura de la cuadrícula. Pueden ser verticales (“líneas de cuadrícula de columna”) u horizontales (“líneas de cuadrícula de fila”) y residir a ambos lados de una fila o columna.

- **Track** es prácticamente varias celdas adyacentes o juntas en una fila o columna, como también pueden ser 3, 2 o las celdas adyacentes que se necesita.

- **Area** El espacio total rodeado por cuatro líneas de cuadrícula. Un área de cuadrícula puede estar compuesta por cualquier número de celdas de cuadrícula. Esta propiedad también se puede utilizar para asignar un nombre a un elemento de la cuadrícula.

- **Cell** son cada cuadro de la grilla, como lo son en una tabla, como la de excel.

- **Grid row** cuando pensamos en grid row vamos a pensar de forma vertical y empezamos a contar desde la linea 1 a la linea 6 (arriba a abajo)

- **Grid column** cuando pensamos en grid column vamos a pensar de forma horizontal y empezamos a contar de la línea 1 a la línea 6 (izquierda a derecha)

- **Axis** es la alineación del contenido dentro o items o celdas de nuestra grid

- **Row axis** este eje es de forma horizontal o también lo podemos conocer como inline axis

- **Column axis** este eje es de forma vertical también lo conoces como block-axis

## ¿display: grid o display: inline-grid?

**Display**: Desplegar, colocar a la vista, exhibir, lucir, Mostrar, presentar.

**Outer**: Denota cómo se comporta un elemento en relación a los otros.

**Inner**: como se comportan los hijos directos del elemento.

- **Display**: Define el tipo de visualización de un elemento

  - Valores:
    - Inner
    - Outer

- Los valores block e inline definen dos cosas

  - Valor externo (Outer)
  - Valor interno (Inner)

- Cuando usamos **display: grid;** estamos diciendo **display: block grid;**. Es decir que su comportamiento externo sera de tipo bloque

- Un elemento que tenga los atributos de bloque puede tener:

  - Margin y padding
  - width
  - height

- Si pensamos en **display: inline-flex;** su relación con otros elementos no sera de bloque sino de línea.

## Finalize este curso en 5h
