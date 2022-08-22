Los selectores identificara los elementos de HTML para darle estilos a través de CSS, por lo que existen diferentes selectores con cuales jugar un poco. Los tipos de selectores son los siguientes:

1. Selector Universal `*`

2. Selector de Etiqueta

3. Selector de Id `#`

4. Selector de Clase `.`

5. Selector Anidado

6. Selector Hijo `>`

7. Selector Adyacente `+`

8. Selector de Atributo `input(type="number")`

## Selector Universal

Utilizaremos el signo de asterisco `*` para identificar el selector universal, este nos indica que todos los elementos de HTML tendrán la configuración de la propiedades que tenga este selector. 

Por ejemplo, si coloco `margin:0` y `padding:0` en las propiedades este selector, todos los elementos no tendrán un margen y tampoco un espaciado interno. 

```css
*{
    margin:0;
    padding:0;
}
```

En esta etiqueta se debe tener cuidado, debido a que como dijimos se modifica todo los elementos HTML, por lo general usamos esta etiqueta para normalizar o reseteo de estilos de nuestro CSS, de esta manera se resetea los estilos por defecto que los navegadores pueden imponer de acuerdo a sus estándares de renderización. 

Puedes encontrar mas información de la normalización del CSS en este [enlace](https://necolas.github.io/normalize.css/).

## Selector de etiqueta

El selector de etiqueta sera aquel selector que identificara una etiqueta de HTML, por ejemplo las etiquetas de párrafo `<p> Un párrafo </p>` podemos darle estilo haciendo un llamado a `p` en la hoja de estilos de CSS. Tambien se puede utilizas las comas (,) para colocar estilos a varios selectores de etiqueta.

```css
p{
    color:blue
}
h1,h2,h3,h4,h5{
    font-family: Arial, Helvetica;
    color:black;
}
```

## Selectores de Id

El selector de Id es aquel que identifica a un elemento de HTML que contenga el atributo de Id, se identifica a este selector por el signo de hash `#`, por ejemplo si tengo un codigo HTML, como:

```html
<body>
<p>Soy color Azul</p>
<p id="verde">Soy Verde</p>
</body>
```

Para darle estilos de color verde a la etiqueta `p` con atributo `id` en CSS realizo:

```css
p{
    color:blue
}
#verde{
    color:green
}
```

## Selector de Clase

Es muy usual que en vez de utilizar el atributo de `id` es sugerible usar el atributo `class`. Aqui utilizaremos el signo del punto `.`. Un ejemplo práctico es:

```html
<body>
<p>Soy color Azul</p>
<p class="verde">Soy Verde</p>
</body>
```

Para darle estilos de color verde a la etiqueta `p` con atributo `class` en CSS realizo:

```css
p{
    color:blue
}
.verde{
    color:green
}
```

## Selectores Anidados

El selector anidado es para realizar una especificidad al selector que estamos escogido a darle estilos, un ejemplo para comprenderlo es el siguiente: Si tenemos un codigo HTML como:

```html
<body>
<span>Soy color negro</span>
<p>
    <span>Soy Rojo</span>
</p>
</body>
```

Vemos que tenemos una primera etiqueta `span` y luego otra etiqueta de párrafo `p` y dentro de esta etiqueta se encuentra otra etiqueta `span`, ahora que pasa si yo quiero únicamente darle color rojo al `span` que se encuentra dentro de la etiqueta párrafo, pues utilizo un selector anidado en CSS, de la siguiente forma:

```css
span{
    color:black
}
p span{
    color:red
}
```

## Selector de Hijos

Aplicamos los estilos a los elementos HTML que sean hijos directos. Utilizo el 
Por ejemplo para un HTML:

```html
<body>
  <p><span>Soy color rojo</span></p>
  <p><div><span>Soy verde</span></div></p>
</body>
```

Si deseo darle estilos a los hijos directos de la etiqueta `p` que sean `span`, ocuparia el simbolo `>`, de manera que:

```css
p > span{
    color:red;
}
span{
    color:green;
}
```

Aquí aplicaría los estilos al span que esta dentro de `p` osea en `<p><span></span></p>`, no aplicaría en la etiqueta de `<p><div><span></span></div></p` debido a que el hijo directo es `<div>` y no `<span>`, por lo que en ese caso no se aplicarían los estilos.

## Selector Adyacente

Este selector referencia a un elemento que esta precedido por otro elemento, es decir ambos deben compartir el mismo elemento padre.

```html
<body>
  <h2>Soy color negro</h2>
  <h2>Soy rojo</h2>
</body>
```

En este caso usamos el selector `h2 + h2` de manera que queremos darle estilos al segundo `h2` con el color rojo.

```css
h2{
    color: black
}
h2 + h2{
    color: red
}
```

Podemos jugar mas con este tipo de selector, por ejemplo si tenemos 5 etiquetas `h2`, para darle estilo al 5to elemento usamos en CSS como `h2 + h2 + h2 + h2 + h2{}`.

## Selector de atributo `input[type="number"]`

Cuando deseemos encontrar el elemento exacto que queramos modificar, hacemos uso de los corchetes `[]` para identificar un elemento de atributo. Por ejemplo para un HTML:

```html
<input type="number">
<input type="email">
```

Si tenemos dos `inputs` en HTML, pero con distinto tipo de entrada, en este caso numérico y de correo electrónico. Si queremos darle un borde negro al `input` numérico haremos uso de los corchetes `[type='number']` que agregaremos a nuestro selector. 

De igual forma lo realizaremos para el `input` de correo electrónico, que queramos darle un borde de color rojo usaremos los corchetes `[type='email']` para especificar ese `input`.

```css
input[type='number']{
    border:black
}
input[type='email']{
    border:red;
}
```

## Prioridad en una regla de CSS

La prioridad de una regla de CSS va en un orden establecido de acuerdo al navegador, esto nos indicara que cual es el estilo que prefiere colocar en un elemento HTML el navegador.

Estos se dan de acuerdo al tipo de selector que yo este usando, y estos son valores básicos que dan prioridad los navegadores:

Id = 100

Clase = 10

Etiquetas = 1

Una recomendación para priorizar es utilizar los atributos `class` para darle estilo a un elemento HTML. Revisemos un ejemplo de prioridad de regla CSS:

```html
<body>
<h2>Soy color negro</h2>
<h2 class="especial"><span>Soy Especial </span><h2>
<h2 id="superespecial"><span>Soy super especial</span></h2>
</body>
```

Si generamos los estilos css, por ejemplo:

```css
span{
    color:black;
}==1
h2.especial span{
    color:red;
}==12
h2#superespecial span{
    color:green;
}==102
```

Aquí observamos el primer selector de etiqueta es `span`, es tendrá un valor de 1. Mientras que el segundo selector es uno de clase `h2.especial` con prioridad $prioridad=10$ y a su vez de etiqueta `h2` con $prioridad=1$ y por ultimo de etiqueta `span` con $prioridad=1$, si sumamos tendremos $10+1+1=12$ de prioridad de toda la regla de CSS.

Finalmente el ultimo selector esta configura con un selector de etiqueta `h2` (prioridad=1), uno de id `#superespecial` (prioridad=100) y otro de etiqueta `span` (prioridad=1) utilizando la anidación, sumamos las prioridades $1+100+1=102$ de prioridad de toda la regla de CSS.

De esta menera la 3ra regla tendra mas prioridad, luego le seguira la 2da regla y por ultimo la primera regla.

Ahora un ultimo ejemplo en CSS a analizar:

```css
h2.especial span{
    color:red;
}
.especial span{
    color:black;
}
```

Si analizamos los valores de prioridad par a la primera regla de CSS, tendremos que hay un selector de etiqueta `h2` (prioridad=1), una clase `.especial` (prioridad=10) y un selector de etiqueta `span` (prioridad=1), sumamos y obtenemos una prioridad de 12.

Para la segunda regla tendremos un selector de clase `.especial` (prioridad=10) y un selector de etiqueta `span`, sumando $10+1=11$ de prioridad en esta regla. De esta manera nuestro estilo de `h2` seguirá la regla con mas prioridad, en este caso la primera regla con prioridad 12.

Existe un elemento mas que tiene una prioridad mas alta y es el `!important` con prioridad de 1000000 es decir un millón. Su uso seria así:

```css
span{
    color: black !important;
}
```

No es recomendado realizar este elemento, únicamente se utiliza en proyecto que no tengamos acceso al código fuente, como por ejemplo en la maquetación de correos electrónicos. Pero si tienes tu propio código no es sugerible utilizarlo.
