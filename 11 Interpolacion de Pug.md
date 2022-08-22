En Pug para referencia a una etiqueta un selector de tipo clase de CSS, debemos concatenar a la etiqueta con un punto `.` y el nombre de la clase seguido. De manera que:

```pug
a.boton
section.intro
```

Equivalente en HTML a:

```html
<a class="boton"></a>
<section class="intro"></section>
```

Ahora que sucede si unicamente colocamos el selector de clase CSS, como por ejemplo `.intro__imagen`?. Pues Pug interpretara que lo que quisiste colocar fue una etiqueta `div` con la clase de `.intro__imagen`, de esta manera en pug:

```pug
.intro__imagen
.intro__contenido
```

En html seria equivalente a:

```html
<div class="intro__imagen"></div>
<div class="intro__contenido"></div>
```

## Anidación de estiquetas directas
Otra forma de anidar etiquetas es utilizar `:` y colocar seguido la etiqueta hijo, por ejemplo si deseamos colocar una etiqueta `div` con clase `.intro__imagen` y dentro de ella una imagen, codificariamos:

```pug
.intro__imagen: img(src="imagen.png")
```

Equivalente en Html

```html
<div class="intro__imagen">
	<img src="imagen.png" />
</div>
```

:::(Info) (Importante)
Esta anidación unicamente funciona para un solo hijo directo.
:::

## Texto en multiples Lineas

Cuando tenemos demasiado texto, tratamos de colocarlo en multiples lineas, a traves de `|` podemos crear multiples lineas de texto que podemos colocar en nuestro contenido, por ejemplo si tenemos un texto *Lorem* tendriamos en pug:

```pug
p 
	| Lorem, ipsum dolor sit amet 
	| consectetur adipisicing elit. 
	| Consequatur nam ducimus 
	| excepturi quia quasi 
	| praesentium aspernatur 
	| dignissimos autem est, 
	| cumque voluptas minus amet 
	| numquam aliquid deleniti 
	| expedita illo obcaecati 
	| architecto.
```
Equivalente en HTML a:
```html
<p>
Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatur nam ducimus excepturi quia quasi praesentium aspernatur dignissimos autem est, cumque voluptas minus amet numquam aliquid deleniti expedita illo obcaecati architecto.
</p>
```
Tenemos que tener cuidado con la indentación, a partir de el podemos agregar otras etiquetas hijos, por ejemplo de la anterior etiqueta `p` podemos colocar una etiqueta `span` como hijo. de panera que:
```pug
p 
	| Lorem, ipsum dolor sit amet 
	| consectetur adipisicing elit. 
	| Consequatur nam ducimus 
	| excepturi quia quasi 
	| praesentium aspernatur 
	| dignissimos autem est, 
	| cumque voluptas minus amet 
	| numquam aliquid deleniti 
	| expedita illo obcaecati 
	| architecto.
    span Lorem ipsum dolor sit amet consectetur 	adipisicing.
```
Que en html seria:
```html
<p>
  Lorem, ipsum dolor sit amet 
  consectetur adipisicing elit. 
  Consequatur nam ducimus 
  excepturi quia quasi 
  praesentium aspernatur 
  dignissimos autem est, 
  cumque voluptas minus amet 
  numquam aliquid deleniti 
  expedita illo obcaecati 
  architecto.
  <span>
    Lorem ipsum dolor sit amet consectetur  	adipisicing.
  </span>
</p>
```

**Contribución realizada por:** David Castillo