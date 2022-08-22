Si decides **compilar por linea de comandos** este preprocesador, entonces la instalación de Pug en los proyectos de JS, lo instalamos por `npm`, de manera que:

```bash
npm install pug
```

Para hacer uso de un CLI en la compilación instalamos la utilidad `pug-cli` por `npm` de manera global.

```bash
npm install pug-cli -g
```

Para ver todos los comandos de la utilidad de `pug` ejecutar `pug --help`, para la **compilación** se realizar:

```bash
pug -w -P [Archivo.pug]
```

:::(Info) (Información)
Recuerda que si utilizas prepros no tienes que instalar pug en tu proyecto, únicamente debes adjuntar tu carpeta a los proyectos de prepros.
:::

## Sintaxis en Pug

En Pug no es necesario realizar una apertura y cierrre de etiqueta `<h1></h1>`, en lugar de eso se usara unicamente el nombre de la etiqueta seguido del contenido, tambien se hace uso de la identación para definir jerarquía. Para pug crear un encabezado `h1` y parrafo `p` sera:

```pug
h1 Titulo
p Lorem ipsum
span Boton
```

Relizando la compilación `.pug` a `.html` el código equivalente en HTML sera:

```html
<h1>Titulo</h1>
<p>Lorem ipseum</p>
<span>Boton</span>
```

### Jerarquia de etiquetas en Pug

Si deseamos crear anidación de etiquetas `<div><ul><li></li></ul></di>` y que exista una jerarquia entre ellas, Pug hace uso de la **identación** para definir la jerarquia, debemos tener sumo cuidado con la identación ya que el pseudocodigo respeta estrictamente las identaciones y en la hora de la compilación realizara una respectiva revisión de esta sintaxis.

Para la identación puedes usar unicamente *tabs* o espacios realizados por la tecla *space*, pero no mezcladas. Asi que debes definir un estandar a la hora de realizar una identación.

```pug
div
 span
```

```html
<div>
  <span></span>
</div>
```

Recuerda que en VSCode pude definir la equivalencia de espacios con tabs en la parte inferior derecha `Tab Size:4`, definelo de acuerdo a lo que requieras.

### Estructura completa de HTML en Pug

Para definir el tipo de archivo HTML en Pug codificamos `doctype html`, y luego generamos la etiqueta padre `html` junto con `head` y sus etiquetas `meta`. En las etiquetas `meta` para definir sus atributos se usa paréntesis y dentro de ellos los atributos que se quiere agregar, de manera que `meta(charset='UTF-8')`. 

De la misma forma para extraer el archivo de estilos `ejercicio-pug.css` a través de `link`.

```pug
link(rel="stylesheet",href="./css/ejercicio-pug.css")
```

equivalente en html a:

```html
<link rel="stylesheet" href="css/ejercicio-pug.css">
```

Otras formas de añadir atributos y multiatributos en pug seria:

```pug
link (
    rel="stylesheet"
    href="./css/ejercicio-pug.css"
)
```

Despues definimos la etiqueta de `body` y la sección de `header`.

```pug
doctype html
html
    head
        meta(charset="UTF-8")
        link(rel="stylesheet",href='css/ejercicio-pug.css')
    body
        header
            h1 PlatziGames
            a.boton Registro
            div
                span Boton
            div
                a Boton 2
```

Equivalente en HTML a:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="css/ejercicio-pug.css">
  </head>
  <body>
    <header>
      <h1>PlatziGames</h1><a class="boton">Registro</a>
      <div><span>Boton</span></div>
      <div><a>Boton 2</a></div>
    </header>
  </body>
</html>
```

### Interpolación de Atributos

Pug al ser basado en Javascript, podemos hacer uso de las variables primitivas, por cuanto para definir una variable usaremos un guion `-` y usamos la sintaxis de Javascript para generar la variable, por ejemplo par aun enlace `-var url=""` y depues pasamos la variable por el atributo de la etiqueta.

En pug:

```pug
-var url = "https://google.com";
a(href=url) Google
```

En Html:

```html
<a href="https://google.com">Google</a>
```

# 

**Contribución realizada por:** David Castillo
