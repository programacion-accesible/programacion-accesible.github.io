---
layout: post
title: Desarrollo de complemenos para NVDA
category: comunidad
tags: [NVDA, complementos, módulos, python]
author: Gera Kessler
excerpt: Elementos básicos para la creación de módulos globales o de aplicación para el lector de pantallas NVDA
---

Los complementos son extensiones de software que se pueden agregar al lector de pantallas NVDA (NonVisual Desktop Access) con el fin de ampliar sus capacidades y funcionalidades.

Realizar complementos para NVDA no es en rigor algo sencillo. La documentación escasea, y la curva de aprendizaje es un poco pronunciada.
La idea de estos ejemplos es orientar en los primeros pasos a los interesados dotándolos de herramientas para comenzar y que no caigan al primer intento.

### Consejos iniciales y recursos

En primer lugar es fundamental ser conscientes de que antes de pretender crear scripts o módulos es imprescindible tener un buen manejo de NVDA.
Para evitar crear herramientas ya integradas, o que ya existen en otros complementos. Asimismo tener en claro hasta donde es posible o no llegar con una herramienta como esta.
El código que se utiliza es fundamentalmente python, por lo que es importante tener los conocimientos necesarios del lenguaje. Principalmente el paradigma de objetos que es en lo que se basa este software y sus complementos.

La guía del desarrollador traducida puede encontrarse en la [comunidad de NVDA en español.](https://nvda.es/documentacion/desarrollo/guia-del-desarrollador-de-nvda/)  
El repositorio del proyecto NVDA en github tiene el código fuente de los módulos integrados que son un recurso importante.
[NVDA en GitHub](https://github.com/nvaccess/nvda)

Los complementos también son una buena fuente, aunque es conveniente revisar los más simples para ir conociendo poco a poco los módulos y funcionalidades integradas. La ruta donde se alojan los ya instalados es:

    %AppData%\nvda\addons

Para revisar un complemento sin instalarlo tan solo es necesario cambiar la extensión del archivo a zip y descomprimirlo.

## Carpeta Scratchpad

Este directorio de NVDA alojado entre los archivos de configuración del usuario es una opción útil para probar el código durante el desarrollo.
Para poder utilizarlo es necesario activarlo y hacerlo visible desde la configuración de NVDA:

* Abrir el menú de NVDA, preferencias, opciones
* En la categoría avanzado, activar la casilla "Comprendo que cambiar estas opciones puede hacer que NVDA funcione incorrectamente"
* Activar la casilla "Habilitar la carga de código personalizado desde el directorio Developer Scratchpad"
* Aplicar cambios
* Activar la opción "Abrir el directorio developer scratchpad"

La ruta de este directorio es la siguiente:

    %AppData%\nvda\scratchpad

Dentro de este directorio se encuentran las carpetas "appModules", para los módulos de aplicación, y "globalPlugins" para los mólulos globales.
Para hacer que funcionen los módulos una vez pegados en el directorio correspondiente, es necesario recargarlos con el atajo "NVDA + control + f3" o reiniciando NVDA.
Es importante recordar que una vez realizada las pruebas hay que  limpiar estos directorios para que no queden cargados scripts innecesarios que pueden perjudicar el buen funcionamiento del lector de pantallas.

### Base para módulos de aplicación o mólulos globales

Cuando la intención es crear scripts para una aplicación determinada, hay que crear un archivo con extensión py que tenga el nombre del ejecutable de la aplicación y pegarlo en el directorio AppModules.
El nombre del ejecutable podemos obtenerlo pulsando "NVDA + control + f1" con la app enfocada. El archivo py requiere que el nombre esté escrito en minúsculas, por ejemplo:

* Bloc de notas; notepad.py
* Google Chrome; chrome.py
* SoundForge 17; forge17.py

En el caso de los módulos globales, estos pueden tener cualquier nombre, preferentemente algo que defina su funcionalidad. Deben ser ubicados en el directorio globalPlugins

### Repositorio Git y Scratchpad

En el caso de utilizar un repositorio git para desarrollar el proyecto de complemento y poder realizar las pruebas pertinentes, es conveniente crear un enlace simbólico de la carpeta donde se aloja el script python.  
En el caso de tener el repositorio en la ruta %UserProfile%\repositorios\mi-complemento, el comando sería el siguiente

    mklink /d %Appdata%\nvda\scratchpad\appModules\mi-complemento %UserProfile%\repositorios\mi-complemento

Esto permite que podamos hacer cambios y commits desde el repositorio, y probar los cambios en el programa.

### Audio demostración

En el siguiente audio demuestro algunos detalles a tener en cuenta a la hora de crear un módulo de aplicación para interactuar con la interfaz de una aplicación utilizando el navegador de objetos, y la consola integrada de NVDA.

[Reproducir en una nueva pestaña](http://gera.ar/player?id=addons&title=Desarrollo%20de%20complementos%20para%20NVDA){target="_blank" title="Se abre en nueva pestaña"}
