Los `includes` permiten insertar el contenido de archivos `.pug` en otros archivos `.pug`. Por ejemplo si tenemos ya diseñado nuestra pagina home en un solo archivo, podemos dividir cada una de las partes de nuestra pagina y guardarlos en otros archivos `.pug`, y luego hacer un llamado a traves `include`.

Por ejemplo si tenemos el archivo general:

```pug
-var titulo = "Subtitulo Principal"
-var titulos = ["Titulo Principal","Subtitulo 1","Subtitulo 2","Subtitulo 3"]
-var usuario = 'David'
mixin caja(imagen,titulo,contenido)
	.caja
		.caja__imagen: img(src="images/"+imagen)
		.caja__contenido
			h3=titulo
			p=contenido

doctype html
html
	head
        meta(charset="UTF-8")
        link(rel="stylesheet",href='css/ejercicio-pug.css')
        title Uso de Preprocesadores
	body
		header
			h1 PlatziGames
			h2 #{titulo}
			if usuario
				a Hola #{usuario}
			else
				a.boton Registro

		section.intro
			.intro__imagen: img(src="images/imagen.png")
			.intro__contenido
				h2 Titulo Principal
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
					span Lorem ipsum dolor sit amet consectetur adipisicing.

				a.boton Leer Mas
		main.contenido
			each titulo in titulos
				+caja("imagen.png",titulo,"Contenido 1")

		footer
            ul
                li Home
                li About me
                li Contacts
                li Blog
                li Policy
```

## Uso de `include`

La sintaxis para el uso de `include` es:

```pug
include ./include/head.pug
include ./include/content.pug
include ./include/footer.pug
```

Ahora utilizando el código anterior, podriamos dividir a nuestro archivo general `.pug` en tres partes:

1. Cabecera (head)
2. Contenido (body)
3. Pie de Pagina (footer)

entonces lo que realizariamos es crear 3 archivos `.pug` para cada una de estas partes, de manera que tendriamos `head.pug`, `landing.pug` y `footer.pug`, y lo que haremos es llamar a los archivos de `head.pug` y `footer.pug` dentro de `landing.pug` a traves del comando `include`.

En `landing.pug`:

```pug
doctype html
html
	include ./head.pug
	body
		header
			h1 PlatziGames
			h2 #{titulo}
			if usuario
				a Hola #{usuario}
			else
				a.boton Registro

		section.intro
			.intro__imagen: img(src="images/imagen.png")
			.intro__contenido
				h2 Titulo Principal
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
					span Lorem ipsum dolor sit amet consectetur adipisicing.

				a.boton Leer Mas
		main.contenido
			each titulo in titulos
				+caja("imagen.png",titulo,"Contenido 1")

		include ./footer.pug
```

En `head.pug`:

```pug
head
    meta(charset="UTF-8")
    link(rel="stylesheet",href='css/ejercicio-pug.css')
    title Uso de Preprocesadores
```

En `footer.pug`:

```pug
footer
    ul
        li Home
        li About me
        li Contacts
        li Blog
        li Policy
```

Podemos dividir a nuestro código cuantas veces queramos, y usar nuestros `includes` cuantas veces queramos. (Si ya has usado react, te sonara un poco parecido a la forma de esta estructuración).

## Uso de `extends` y `block`

El usar `extends` y `block`, nos proporciona un concepto conocido como **herencia de plantilla**. En la herencia de plantilla un bloque de código que se colocara en una posición en la página, como lo nombre lo dice usaremos bloques de codigo para generara una **plantilla**, este proceso se basa en la  **recursividad**.

En otras palabras podremos ir construyendo un formato de acuerdo a bloques y la posición de los mismos, y despues utilizar esta plantilla con distintos contenidos. Un ejemplo rapido seria la división del header y el contenido.

```pug
//- header.pug
block head
	doctype html
	html
		include ./head.pug
		body
			header
				h1 PlatziGames
				h2 #{titulo}
				if usuario
					a Hola #{usuario}
				else
					a.boton Registro
```

```pug
//- layout.pug
extends header.pug
block head
			section.intro
						.intro__imagen: img(src="images/imagen.png")
						.intro__contenido
							h2 Titulo Principal
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
								span Lorem ipsum dolor sit amet consectetur adipisicing.

							a.boton Leer Mas
					main.contenido
						each titulo in titulos
							+caja("imagen.png",titulo,"Contenido 1")

					include ./footer.pug
```

El ultimo código renderizamos, ya que este contiene el `extend`.

## Diferencia entre `include` y `extend`:
Es importante que diferenciemos estos keywords, porque tienen un comportamiento que se podria decir que es similar, pero tienen sus diferencias. La diferencia principal es que con `include` estamos traspasado el codigo de otro archivo `.pug` tal como es, es decir transferimos todo el texto plano que se encuentre ahi. Mientras que con `extend` y `block`, podemos subseccionar el codigo por bloques, y un unico archivo simplificado `.pug` para agregar unicamente el contenido y hacer el llamado de los bloques.

**Contribución realizada por:** David Castillo