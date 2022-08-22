BEM por sus siglas en Ingles significa *Block, Element and Modifier*, es una metodología de codificación o también llamada convención de nombres para clases de CSS, esta metodología fue desarrollada por Yandex ("el Google de Rusia") y es ampliamente usada en el mundo del desarrollo web. 

Se usa tanto en proyectos pequeños como en proyectos grandes, y su propósito es dividir de manera lógica las piezas que componen un sitio web. 

## Como trabaja BEM?

Un nombre de clase BEM tiene tres partes:

1. **Bloque:** Se puede identificar como un modulo que no depende de ninguna otra parte de la pagina, su existencia es por su propia autonomía  de código. Y serán bloques individuales que pueden existir en cualquier lugar de la pagina sin necesidad de depender de otras partes de la pagina.
   
   Ejemplos:
   
   - Un menú de navegación
   
   - Una card de presentación
   
   - Una bloque de publicación.

2. **Elemento:** Los elementos serán módulos que dependen del bloque, serán las partes que conforman al bloque.
   
   Ejemplos:
   
   - Los botones que forman el botón 
   
   - Las imágenes de la carta de presentación
   
   - Los iconos de reacción de la publicación.

3. **Modificador:** Los modificadores serán modificaciones de estilo de los elementos, es decir cambiaremos el aspecto del elemento para generar una variación del elemento en cuestión. Esto se utiliza cuando queremos usar los mismos estilos y generar un estado de un elemento.
   
   Ejemplos:
   
   - Cuando un icono cambia de color por alguna reacción en una publicación.

## Sintaxis

La sintaxis con la cual funciona la metodología BEM es la siguiente:

```css
[bloque]__[elemento]--[modificador]{}
```

si utilizamos un selector de clase, tendremos la siguiente sintaxis:

```css
.bloque{}
.bloque__elemento{}
.bloque__elemento--modificador{}
```

de igual forma usaríamos para los selectores id (Aunque como habíamos dicho usar selectores id no es tan recomendable).

Un ejemplo practico, seria si tenemos una galería de fotos:

![](img/2022-08-11-09-32-09-image.png)

Aquí definiríamos a un bloque como la galería completa `.galeria{}`, mientras que un elemento seria la foto que se encuentra como un encabezado de card `.galeria__foto{}`, y una modificación seria si a esta foto la diseñamos con forma circular `.galeria__foto--circular{}`.

Ya usando la metodología BEM totalmente tendríamos:

```css
.galeria{} /* bloque */
.galeria__foto{}  /* elemento */
.galeria__titulo{} /* elemento */
.galeria__descripcion{} /* elemento */
.galeria__foto--circular{} /* modificador */
```

Como recomendación utilizar el ingles para identificar a los selectores, ya que es un estándar en la industria del desarrollo web.

## Ventajas de utilizar la metodología BEM

- Menos repeticiones de código, con la metodología BEM podemos generar una codificación menos repetitiva, dado a que daremos nombres a las clases de acuerdo a contenedores y ligeras modificaciones cuando necesitemos de un nuevo modulo.

- Componentes autónomos e independientes, esto nos ayuda a que nuestros modulos creados sean unicos y no dependan de otro codigo externo al componente que se pretende construir.

- Herencia múltiple única de cada componente.

