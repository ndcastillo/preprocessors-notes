Para comenzar a ver los preprocesadores es importante saber correctamente el uso de HTML y CSS nativo, por lo que en esta clase se revisara una breve introducción a CSS.

CSS son hojas de estilo en cascada, o también en ingles *Cascading Style Sheets*, y a través de el podemos generar estilos y diversas vistas al código HTML. Te puedes imaginar la siguiente analogía: Se tiene una casa super genial, las paredes, estructura y forma sera el HTML, mientras que el diseño de interiores, pintura y acabados serán el CSS.

## Formas de Incluir CSS

Existen tres formas de incluir CSS a un código HTML:

**1. En el mismo Documento**

La primera forma es incluir en el propio documento HTML, embebiendo en la etiqueta `<style></style` en el propio archivo HTML.
Aunque no es una buena práctica, si son estilos sencillos, de prueba o compactos es una forma de introducir CSS, esta forma es muy usada en la maquetación de correos electrónicos.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Incluir CSS en el mismo documento HTML</title>
    <style>
        p{
            color: black;
            font-family: Verdana;
        }
    </style>
</head>
<body>
<p>Un párrafo de texto.</p>
</body>
</html>
```

**2. En los elementos HTML**
La segunda forma es introducir las propiedades de estilo en las propias etiquetas HTML, esto con el uso del atributo `style=''` en la propia etiqueta que deseamos estilizar. Si es una página sencilla o una maquetación de un correo electronico, esta forma es muy conveniente, pero no se sugiere si el proyecto tiene que ser escalable y sostenible.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Incluir CSS en los elementos HTML</title>

</head>
<body>
    <p style="color:black; font-family:Verdana;">Un párrafo de texto.</p>
</body>
</html>
```

**3. En un archivo externo**

La tercera forma y la mas utilizada y también recomendada es hacer un llamado a un documento de extensión `.css`  a través una especificación de relación entre el documento HTML y un recurso externo CSS, esto se realiza a través de la etiqueta `<link>`. Esta forma es recomendada debido a que es escalable, sostenible y que separa el código HTML y el CSS en documentos independientes.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Incluir CSS en un archivo externo</title>

    <link rel="stylesheet" href="css/estilos.css">

</head>
<body>
    <p>Un párrafo de texto.</p>
</body>
</html>
```

Se recomienda separar tanto el contenido y los estilos en documentos distintos, debido a que lo que importa es el resguardo del contenido.

## Sintaxis

En la sintaxis basica de CSS se compondrá por una regla, la cual tendrá dos partes, **el selector** y **la declaración**.

El **selector** sera la identificación del elemento de HTML a la cual deseas darle estilo en CSS, mientras que la **declaración** serán las propiedades que se le dan al elemento. En la declaración tendrá el nombre de la **propiedad** `color` y el **valor de la propiedad** `blue`.

```css
h1{
    color:blue
}
```

Si aplicamos la regla de CSS anterior a nuestro documento HTML, obtendremos que todos los títulos `h1` tendrán un color azul. Hay que mencionar que muchos selectores y que estos a su vez puede tener una infinidad de propiedades. 

Las propiedades de un selector pueden ser diversas dependiendo del elemento al cual queramos estilizar, así es como podemos cambiar tipografías, colores, posicionar, configurar bordes, animar cajas entre otras. Es por ello que través de propiedades y valores se pueden generar grandiosas vistas con CSS.


