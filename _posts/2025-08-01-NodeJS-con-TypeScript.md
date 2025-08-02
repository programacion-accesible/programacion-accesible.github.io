---
layout: post
title: Node.js 24.5 ahora ejecuta TypeScript de forma nativa
date: 2025-08-01 21:00:00 -0300
author: Miguel Barraza
category: noticias
tags: [nodejs, typescript, javascript]
excerpt: Node.js ya permite ejecutar archivos .ts directamente sin instalación adicional; solo se eliminan anotaciones de tipo en tiempo de ejecución.
---

La versión 24.5 de Node.js, lanzada el 31 de julio de 2025, incorpora de forma predeterminada el soporte para ejecutar archivos `.ts` (TypeScript) sin herramientas adicionales. Esto permite a los desarrolladores ejecutar directamente código TypeScript sin necesidad de compilarlo o usar herramientas como `ts-node`.

## ¿Qué cambia?

* Ahora es posible ejecutar archivos `.ts` directamente con `node archivo.ts`.
* Las anotaciones de tipo se eliminan automáticamente, sin intervención del desarrollador.
* La opción `--no-experimental-strip-types` permite desactivar este comportamiento si se desea.
* Para ejecutar ciertas características avanzadas de TypeScript, como `enum` o `namespace`, se debe utilizar la bandera `--experimental-transform-types`.
* Node.js sigue sin interpretar configuraciones definidas en `tsconfig.json`.

## Ejemplos de uso

### Ejemplo básico sin transformaciones

```ts
// hola.ts
const mensaje: string = 'Hola desde TypeScript';
console.log(mensaje);
```

Ejecución:

```
node hola.ts
```

Esto imprime:

```
Hola desde TypeScript
```

### Ejemplo con `enum` (requiere flag)

```ts
// opciones.ts
export enum Rol {
  Admin,
  Usuario
}

// app.ts
import { Rol } from './opciones.ts';
console.log(Rol.Usuario);
```

Ejecución:

```
node --experimental-transform-types app.ts
```

Este comando permite procesar `enum` y otras estructuras que generan código JavaScript.

## Limitaciones

* No hay verificación de tipos en tiempo de ejecución.
* No se interpretan configuraciones de `tsconfig.json`, como alias o decoradores.
* Características como JSX, paths personalizados o transformaciones complejas requieren herramientas externas.
* Esta funcionalidad sigue siendo experimental y puede cambiar en futuras versiones.

## Buenas prácticas

1. Usar la ejecución nativa solo para scripts o pruebas rápidas.
2. Mantener `tsc` para validación de tipos durante el desarrollo.
3. Evitar depender de esta funcionalidad en producción hasta que se estabilice.
4. Seguir utilizando compilación tradicional para proyectos complejos o bibliotecas.
5. Verificar compatibilidad si se usan estructuras avanzadas como `enum` o `namespace`.

## Conclusión

Node.js 24.5 simplifica el desarrollo con TypeScript al permitir ejecutar archivos `.ts` sin herramientas adicionales. Esta funcionalidad mejora la experiencia para scripts y prototipos, aunque su uso en producción todavía requiere precauciones. A medida que el soporte evolucione, podría convertirse en una alternativa viable para más escenarios.

## Glosario técnico

* **Type stripping**: proceso mediante el cual se eliminan las anotaciones de tipo antes de ejecutar el código.
* **experimental-transform-types**: bandera que habilita la transformación de sintaxis TypeScript que genera código, como `enum`.
* **tsconfig.json**: archivo de configuración del compilador TypeScript.
* **Type checking**: verificación de tipos mediante el compilador, que no se realiza automáticamente en tiempo de ejecución.
* **Erasable syntax**: sintaxis que no genera código en JavaScript y puede eliminarse sin afectar el funcionamiento del programa.

## Fuentes:

1. Node.js 24.5.0 Released
   [https://nodejs.org/en/blog/release/v24.5.0][]
   Node versión oficial  con cambios destacados, incluido el soporte nativo para TypeScript.

2. Node.js TypeScript Support Documentation
   [https://nodejs.org/api/typescript.html](https://nodejs.org/api/typescript.html)
   Documentación oficial sobre la ejecución de archivos TypeScript en Node.js.

3. Node.js 24: What’s new?
   [https://blog.logrocket.com/node-js-24-features/](https://blog.logrocket.com/node-js-24-features/)
   Análisis de las novedades en Node.js 24, incluyendo el soporte experimental activado por defecto.

4. Understanding TypeScript in Node.js
   [https://2ality.com/2025/01/nodejs-strip-type.html](https://2ality.com/2025/01/nodejs-strip-type.html)
   Explicación detallada del funcionamiento del type stripping y sus limitaciones actuales.
