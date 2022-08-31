La forma de declarar una variable en Pug, es colocar un guion `-` y después declararla como si fuese Javascript. Como buena practica, las variables y mixins deben ser realizados antes de la línea de `doctype html`.

Para llamar a la variable usaremos el símbolo de hash y llaves`#{}` después de la etiqueta donde queremos introducir esa variable, de manera que `#{variable}`. 

Por ejemplo, para un subtítulo podemos generar en pug de la siguiente manera:

```pug
-var titulo = "Sub-titulo Principal"
h2 #{titulo}
```

Otras manera de declarar la variable sera insertar un `=` seguido de la variable, como por ejemplo.

```pug
-var subtitulo = "Subtitulo Principal"
h2=titulo
```
## Uso de Arreglos en Pug

Ahora, si tenemos varios títulos, entonces podemos utilizar un arreglo en Javascript `-var titulos=["","",""]`, y hacer el llamado por cada elemento de acuerdo a su posición `#{titulos[0]}`, `#{titulos[1]}` y `#{titulos[2]}`.

```pug
-var titulos = ["Titulo Principal","Subtitulo 1", "Subtitulo 2"]

h2 #{titulos[0]}
h3 #{titulos[1]}
h3 #{titulos[2]}
```

Con los arreglos podemos generar muchas implementaciones, y también podemos agregar objetos y hacer llamados de los elementos. Por ejemplo:

```pug
-var myCard = {
    'Nombre':'Jio Freed',
    'Email':'jiofreed@email.com',
    'Work':'Developer',
    'Hobbies':'Games,Books'
}

h3 My card
p #{myCard.Nombre}
p #{myCard.Email}
p #{myCard.Work}
p #{myCard.Hobbies}
```

Donde su equivalente html seria:

```html
<h3>My card</h3>
<p>Jio Freed</p>
<p>jiofreed@email.com</p>
<p>Developer</p>
<p>Games,Books</p>
```

**Contribución realizada por:** David Castillo
