---
layout: post
title: Qué es MarkDown y por qué deberías usarlo
category: tutoriales
tags: [markdown, lenguajes-de-marcado]
author: Ulises Milani
excerpt: Aprende a usar MarkDown, el lenguaje de marcado que te permite crear documentos HTML con un formato sencillo y legible, usando sólo texto plano.
---

Si te gusta escribir en Internet, seguramente te habrás encontrado con
la necesidad de usar HTML o CSS para dar formato a tus textos. Estos
lenguajes son muy útiles, pero muchos no tienen el conocimiento
necesario y tienen que recurrir a otras alternativas para poder
publicar. ¿Te gustaría poder escribir tus documentos con un formato
sencillo y legible, usando sólo texto plano? Eso es lo que te ofrece
MarkDown.

MarkDown es un lenguaje de marcado ligero creado por John Gruber y Aaron
Swartz en 2004, que tiene como objetivo simplificar el HTML y permitir
crear contenido de una manera fácil de escribir y de leer.

## ¿Para qué sirve MarkDown?

Sirve para dar formato a cualquier tipo de documento que quieras
publicar en Internet, como publicaciones en blogs, páginas web, foros, documentación y
más.

Usar MarkDown tiene muchas ventajas. Algunas de ellas son:

-   Es fácil de aprender y de usar. No necesitas tener conocimientos previos de HTML o CSS para dar formato a tus textos. Sólo necesitas unos pocos símbolos.
-   Es rápido y eficiente. No pierdes tiempo en diseñar o ajustar el formato de tus textos. Sólo te enfocas en el contenido y en el mensaje que quieres transmitir.
-   Es legible y elegante. Tus textos se ven bien tanto en su forma de entrada como de salida. No hay distracciones ni elementos innecesarios que afecten la lectura o la comprensión de tus textos.
-   Es compatible y accesible. Tus textos se pueden abrir y editar en cualquier plataforma o dispositivo, sin perder el formato original. Además, tus textos se adaptan a las preferencias y necesidades de tus lectores.

### ¿Cuál es la diferencia entre MarkDown y HTML?

En este post te voy a enseñar cómo usar MarkDown. Te voy a mostrar la
sintaxis básica y algunos ejemplos de cómo puedes usarlo. También te voy
a dar algunos recursos para que puedas sacarle el máximo provecho a este
lenguaje. Pero te adelanto que lo que notarás es que MarkDown es una simplificación de HTML.

---

## ¿Cómo usar MarkDown?

Lo primero y muy importante, saber en qué codificación está el
documento. En este caso, el ejemplo va a ser con bloc de notas. Para
saber en qué codificación está el documento, le damos control g o
buscamos en el menú guardar como, y cuando entramos al diálogo buscamos con
tab el cuadro combinado que dice codificación. Si no está en UTF-8
tendremos que ponerlo en esa codificación, porque con otra el MarkDown no
va a funcionar.

Es importante saber que cada vez que hagamos algo en MarkDown, tenemos
que dejar una línea en blanco dando 2 veces enter. Es decir, si queremos
hacer un encabezado y después un párrafo, dar 2 enter después de
terminar el encabezado. Lo mismo para cuando terminamos un párrafo y
queremos iniciar otro.

### Encabezados

Para hacer un encabezado, debemos escribir el signo de almohadilla, dejar un
espacio y poner el texto que queramos que tenga ese encabezado. Cuantos más signos de almohadilla pongamos, mayor va a ser el nivel de
encabezado. Hay hasta el nivel 6 (donde el 1 es el más grande y el 6 es el más pequeño), por lo tanto podremos poner sólo 6
signos de almohadilla. Cada vez que hagamos un encabezado, debemos dejar una línea en blanco
para poner un párrafo.

#### Ejemplo de código

```MarkDown
## Encabezado de nivel 2

Aquí va el siguiente párrafo.
```

### Párrafos y saltos de línea

Los párrafos se escriben normalmente, sin símbolos. Si queremos hacer un salto de línea en un párrafo, tenemos que dejar 2
espacios al final del texto, dar enter y seguir escribiendo.

Para hacer un párrafo nuevo, dar 2 veces enter para dejar una línea en
blanco, y escribir en la segunda línea que se nos creó.

#### Ejemplo de código

```MarkDown
Este texto forma parte del primer párrafo.

Esto ya va en el segundo
y tiene dos líneas.
```

### Listas

#### Listas numeradas

Las listas numeradas se hacen de la misma manera que en Word. Solo se
escribe el 1, un punto y un espacio. De esa manera se te crea la lista. Cada vez que quieras agregar un elemento, lo haces de la misma manera con los números que desees. Por ejemplo:

```MarkDown
1. Este es el primer elemento de la lista numerada.
2. Segundo elemento.
3. Tercer elemento.
```

Algunas variantes de MarkDown (como la que usa GitHub) permiten que puedas poner siempre un uno delante de todos los elementos de la lista. Así no hay que concentrarse en qué número iba en qué elemento. El código sería así:

```MarkDown
1. El primer elemento.
1. El segundo elemento.
1. El tercer elemento.
```

Hay que dejar una línea en blanco entre el último elemento de la lista y lo siguiente que vayamos a poner.

#### Listas con viñetas

Las listas con viñetas se pueden hacer de distintas maneras. La forma
más fácil es con un guion y un espacio. Cada vez que pongas un guion y
un espacio, se te van a ir creando elementos en la lista. Por ejemplo:

```MarkDown
- Éste es el primer elemento de la lista con viñetas.
- Segundo y último elemento.
```

Al igual que con las listas numeradas, también hay que dejar una línea en blanco entre el último elemento de la lista y la siguiente parte del documento.

### Enlaces

Te voy a explicar la forma más sencilla de hacerlo. El resultado lo
podrás ver en el apartado recursos del post.

Para crear un enlace sin que la URL esté visible, tendrás que abrir
corchetes y poner el texto que quieras que se muestre como título del
enlace. Cierras corchetes, abres paréntesis, pegas la URL de la web que
quieras que se muestre en la página y cierras paréntesis.

```MarkDown
[Una página de ejemplo.](https://www.ejemplo.com)
```

## Publicación

Existen páginas que aceptan contenido hecho directamente en MarkDown como foros, sitios de creación de blogs o la propia documentación de los repositorios de GitHub. Si la página donde vas a publicar no soporta MarkDown deberás convertirlo primero a HTML.

## Recursos

### Conversores

-   [TCA convert doc](https://tecnoconocimientoaccesible.blogspot.com/2021/05/tca-convertdoc-12-con-reconocimiento-de.html)
-   [Pandoc, convversor por línea de comandos.](https://pandoc.org/installing.html)

### Tutoriales y guías

-   [El tutorial de tecnoconocimiento accesible.](https://www.youtube.com/watch?v=3K-aFgctmkk)
-   [Charla de NVDA.](https://www.youtube.com/watch?v=mMN39MMN07I)
-   [La guía más completa de MarkDown en español.](https://markdown.es/)
