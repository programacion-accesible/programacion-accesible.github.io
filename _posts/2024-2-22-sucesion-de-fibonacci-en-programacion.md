---
layout: post
title: Explicando la sucesión de Fibonacci en un simple algoritmo
category: programación
tags: [matemática, fibonacci, javascript]
author: Ronny González
excerpt: ¿Alguna vez escuchaste de la sucesión de Fibonacci? ¡Hagamos un algoritmo para que nuestra computadora lo realice por nosotros!
---

Es  una sucesión infinita de números naturales que comienza con 2 números y a partir de estos el siguiente es la suma de los dos anteriores.

Fue creada por el matemático italiano Leonardo de Pisa en el siglo XIII y es ampliamente utilizada en ciencias de la computación, en teoría de juegos, en la configuración de las ramas de los árboles, en dinámica de los huracanes y en la cría de conejos por mencionar algunos.

Esta sucesión es conocida desde hace miles de años y su origen principal proviene de la India pero fue Fibonacci quien al resolver un problema, la dio a conocer en Europa.

Al iniciar la sucesión tenemos los 2 primeros números, el 0 y el 1. Estos, al sumarse nos da 1, ya así se convierte en el tercer término que es el número 1, ya que lo obtuvimos al sumar 0 + 1. Veamos ahora el problema más detallado.

## Problema: Encontrar el número 10 en la sucesión de Fibonacci

Para esto, debemos conocer la fórmula siguiente:
> Cada número es la suma de los 2 anteriores a este, con excepción de los 2 primeros números, que son el 0 y el 1. Teniendo en cuenta esto, empecemos a buscar estos valores.

## Resolviendo el ejercicio sin programación

Antes de implementar nuestra resolución en el código, debemos resolverla en nuestra mente y con papel en mano.

Primero, tenemos los 2 números principales, que son el 0 y el 1. Como habíamos explicado anteriormente, estos al sumarse nos da el tercer valor en la sucesión que vuelve a ser el número 1, ya que lo obtuvimos sumando los dos anteriores (0 + 1).

Ahora, busquemos el número 4: Para ello, tenemos que sumar los 2 anteriores. (1 + 1). El resultado de esta suma es el 2. Guardemos este número para sumarlo con el siguiente valor que vayamos a encontrar.

Para encontrar el 5 en Fibonacci, miremos cuales eran los 2 últimos valores. Teníamos el 2, mismo que ovtuvimos al sumar (1 + 1). ahora, el anterior valor al 2 era el 1, puesto que al sumar estos 2 nos da 3, y ese sería el número 5 en la sucesión.

Para encontrar el 6, seguimos haciendo lo mismo, sumando los 2 anteriores. primero tenemos el 2, que era el valor anterior al 3 que habíamos obtenido al sumar (1 +1). Luego tenemos el 3, que lo obtuvimos sumando (1 + 2). Esos dos valores lo sumamos y obtenemos el 5. Ese es el 6 en Fibonacci.

Para el 7, sumaremos el 5 que acabamos de obtener más el anterior que era el 3 y tenemos el 8. Ese 8 lo guardaremos junto al 5 para obtener el siguiente valor.

Para encontrar el 8, seguimos sumando los 2 anteriores obtenidos en la sucesión. Estos eran el 8 y el 5. Sumando estos tenemos el 13 que se convierte en el 8 en la sucesión.

Para el 9, sumamos el 8 de la sucesión que era el 13 con el 7 de la misma sucesión que era el 8 y tenemos 21. Ese 21 se convierte en el 9 en la sucesión.

Finalmente, para obtener el 10 hacemos lo mismo que hemos venido haciendo con los anteriores, pero en este caso esos anteriores son el 9 y el 8 de la sucesión. Estos eran el 21 y el 13 y ahora al sumarlos tenemos el 34 y se convierte en el tan buscado 10de nuestra sucesión.

Esta sucesión es infinita, por lo que podemos ir sumando valores para encontrar el siguiente. Solo teniendo en cuenta la fórmula.
> Cada número en la sucesión es la suma de los 2 anteriores a excepción de los 2 primeros números.

Ahora, veamos como resolver este problema con código.

## Algoritmo: Diseña un programa que imprima los primeros 10 números en la sucesión de fibonacci

Para este algoritmo, usaremos JavaScript y lo haremos de la siguiente forma:

Usaremos un arreglo o array que contenga los primeros 2 valores iniciales, lo vamos a recorrer y usaremos su propio índice para ir asignando los valores al array de acuerdo a a su posición.

Primero crearemos una función llamada fibo. Esta va a recibir un parámetro que usaremos para pasarle el límite o hasta el valor que queramos llegar, en este caso el 10. A este parámetro lo llamaremos num.

```javascript
function fibo (num) {}
```

Dentro de esta función, definiremos un array con 2 posiciones. 0, 1 y la llamaremos secuencia.

```javascript
let secuencia = [0, 1];
```

Seguimos dentro de la función y crearemos un bucle o ciclo for. Este iniciará en 2, ya que no es necesario iniciarlo en 0, porque estos valores ya están establecidos y lo que buscamos es completar el arreglo con los números de la sucesión. Este for se va a recorrer mientras que  su iterador sea menor a num, que es el parámetro que tiene la función y se aumentará de 1 en 1. Cuando sean iguales, este no continuará ejecutándose y el flujo de ejecución saldrá de el.

```javascript
    for (let i = 2; i < num; i++) {}
```

Dentro del for, haremos lo siguiente:
- el arreglo secuencia será igual a su posición restándole 1 y sumándole el mismo arreglo pero restándole 2 a su posición. Veamos.

```javascript
        secuencia[i] = secuencia[i - 1] + secuencia[i - 2];
```

Por último, salimos del for y retornamos el arreglo secuencia.

```javascript
    return secuencia;
```

¡Listo! Esta es nuestra función que calculará la sucesión de fibonacci por nosotros. Para ver todo esto, mostraremos lo que devuelve esta función por pantalla.

```javascript
console.log(fibo(10));
```

Esto lo que hace es mostrarnos un arreglo con los siguientes valores de la sucesión:
\[0, 1,  1,  2,  3,
  5, 8, 13, 21, 34]

¿Genial verdad? Pueden crear variables he igualarlas a la posición del arreglo menos 1 y menos 2 y luego imprimirlas para que comprueben que está pasando por debajo realmente, que no es más que asignándole al arreglo el valor de las posiciones a partir de 2 y restándole 1 o 2 al índice y reasignándolos.

### Código completo

Aquí está el código completo.

```javascript
function fibo (num) {
    let secuencia = [
        0, 1];
    for (let i = 2; i < num; i++) {
        secuencia[i] = secuencia[i - 1] + secuencia[i - 2];
    }
    return secuencia;
}

console.log(fibo(10));

```

Saludos cordiales.