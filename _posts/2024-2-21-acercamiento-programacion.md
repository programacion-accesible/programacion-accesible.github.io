---
layout: post
title: Un primer acercamiento a la programación
category: programación
tags: [python, matemáticas]
author: Quico Saval
excerpt: Quizá sepas resolver problemas sencillos. Incluso puede que sepas resolverlos con un ordenador. Pero, ¿por qué con programación?
---

Los problemas matemáticos que se les plantean a los niños en el colegio son sencillos de resolver en papel. Por ello, vamos a usar uno de ejemplo para demostrar que podría ser un buen camino para acercarse a la programación.

## Enunciado

Nuestras últimas ventas han generado unos ingresos de 1000 unidades monetarias. Si los gastos han sido cuatro quintos de los ingresos, ¿cuál es el beneficio?

## Análisis

Sabemos que el beneficio se halla restando ingresos menos gastos. Conocemos los ingresos (1000) y, aunque no sabemos cuánto son los gastos, sí que tenemos la fórmula para calcularlos (cuatro quintos de 1000, que son los ingresos).

Por lo tanto, pensamos en calcular primero los gastos y luego hacer la resta para obtener los beneficios.

## Métodos para solucionarlo

### Papel y calculadora

Si estamos resolviendo el problema en papel podemos usar la calculadora para calcular los gastos:

> 1000 * (4/5) = 800

Ahora calculamos el beneficio:

> 1000 - 800 = 200

Y ahora escribimos la solución.

> El beneficio es de 200 unidades monetarias.

Hemos resuelto el problema, pero si cambia alguna de las cantidades tendremos que rehacer todos los cálculos.

### Con una hoja de cálculo

Supongamos que en la celda a1 de nuestra hoja de cálculo escribimos los ingresos (1000). Si queremos calcular los gastos en la celda a2 podemos usar una fórmula como esta:

> =4/5*a1

Si ahora queremos calcular los beneficios en a3 podemos usar una fórmula como la siguiente:

> =a1-a2

Vemos que en las celdas a2 y a3 aparecerán 800 y 200 respectivamente. Las cantidades se han calculado y si cambiamos los ingresos de a1 o la proporción en la fórmula de a2 comprobaremos que los beneficios cambian.

Sin embargo, no hemos podido escribir el texto con la explicación de la solución y, además, hemos tenido que recordar dónde estaba cada dato para lograr construir correctamente las fórmulas.

### Con programación

Para este ejemplo he elegido el lenguaje python, pero cualquiera puede intentar hacer el programa en el lenguaje que esté aprendiendo. No daré ninguna instrucción sobre cómo guardar y ejecutar el archivo. Sólo me centraré en la forma de construir el código con todo lo que sabemos sobre este problema.

Lo primero que entra en juego es un concepto que se repite en todos los lenguajes de programación: las variables. Por simplificarlo mucho, una variable en un lenguaje de programación va a hacer lo mismo que la celda de la hoja de cálculo: contener un dato que le podemos haber dado directamente o que puede haber calculado a partir de una fórmula.

A diferencia de las celdas, las variables pueden (y deben) tener un nombre que sea significativo para quien hace el código. Además, para evitar cualquier problema, no debe contener vocales acentuadas, eñes ni la u con diéresis.

Vamos a hacer una variable que contenga el dato que conocemos: los ingresos.

```python
ingresos = 1000
```

Ahora necesitamos calcular los gastos. Esto es muy fácil, ya que los símbolos que debemos utilizar son los mismos que conocemos de las hojas de cálculo. Obviamente, necesitaremos una variable para almacenarlos, porque los gastos intervienen en la fórmula de los beneficios.

```python
gastos = 4 / 5 * ingresos
```

Como ya tenemos los ingresos y los gastos podemos hacer la resta para calcular los beneficios. Para saber dónde tenemos el resultado de esa operación usaremos otra variable.

```python
beneficios = ingresos - gastos
```

Ya hemos calculado los beneficios, pero para que nos enteremos de ello al ejecutar el programa necesitamos enviar algún texto a la pantalla. Vamos a aprovechar esto para generar la misma explicación que teníamos escrita en el papel en nuestro primer método de resolución.

```python
print(f"El beneficio es de {beneficios} unidades monetarias.\n")
```

Aquí le estamos diciendo que imprima el texto entre comillas y que sustituya la variable beneficios por el valor que tenga en ese momento. el programa completo quedaría así:

```python
ingresos = 1000
gastos = 4/5 * ingresos
beneficios = ingresos - gastos
print(f"El beneficio es de {beneficios} unidades monetarias.\n")
```

Lo que hemos conseguido resolviendo el problema con programación es:

- Sabemos dónde se guarda cada dato porque le hemos dado un nombre comprensible a cada variable.
- Las fórmulas se parecen mucho más a las que encontraríamos en la solución del libro de matemáticas que las de la hoja de cálculo.
- El programa nos da la misma solución redactada que la que se había hecho en papel.
- Se puede cambiar cualquier dato y ver cómo cambian los beneficios.
- Con más conocimientos se puede ampliar la funcionalidad del programa. Por ejemplo, se podría pedir al usuario que introduzca los datos de ingresos y gastos.
