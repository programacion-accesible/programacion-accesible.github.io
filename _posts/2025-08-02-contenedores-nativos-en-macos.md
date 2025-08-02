---
layout: post
title: Framework nativo de contenedores de Apple en macOS
date: 2025-08-02 09:00:00 -0300
author: Miguel Barraza
category: noticias
tags: [macos, contenedores, open_source]
excerpt: Apple lanzó en WWDC 2025 'Containerization', un framework Swift y open source que ejecuta contenedores Linux en macOS con micro-VMs por contenedor, aportando más rendimiento y seguridad.
---

Apple anunció en la WWDC 2025 el nuevo framework **Containerization**, una solución nativa y de código abierto para ejecutar contenedores Linux directamente en macOS, optimizada para Apple Silicon.

A diferencia de Docker o Podman, que usan máquinas virtuales Linux grandes para contener múltiples instancias, Containerization inicia una **micro‑VM por contenedor**. Este enfoque mejora significativamente la seguridad, la privacidad y el rendimiento. Cada contenedor se ejecuta en su propia VM ligera, con un kernel Linux optimizado y un sistema de inicio personalizado escrito en Swift, capaz de arrancar en milisegundos.

El proyecto se compone de dos componentes abiertos disponibles en GitHub: la biblioteca en Swift **Containerization** y la herramienta de línea de comandos **container** para macOS.

## Instalación y comandos básicos

La instalación se puede realizar fácilmente mediante Homebrew (requiere macOS 15 o superior):

```bash
brew install container
container system start
```

Comandos principales:

* `container system start` / `stop`: inicia o detiene el entorno de contenedores.
* `container image pull <imagen>`: descarga una imagen compatible (por ejemplo, `nginx`, `ubuntu`).
* `container run -i -t <imagen>`: ejecuta la imagen en modo interactivo.
* `container create <imagen>`: crea un contenedor.
* `container list`: muestra contenedores activos y sus direcciones IP.
* `--volume origen:destino`: permite compartir carpetas entre el sistema y el contenedor.

Cada contenedor obtiene una dirección IP única, eliminando la necesidad de vincular puertos. Además, se pueden ejecutar distribuciones populares como Ubuntu, Alpine o Kali Linux, con posibilidad de actualizar paquetes e instalar software adicional.

## Características y limitaciones

### Ventajas

* **Seguridad mejorada**: cada contenedor corre en una VM aislada.
* **Rendimiento elevado**: arranque instantáneo con mínima sobrecarga.
* **Privacidad reforzada**: acceso limitado a recursos compartidos.
* **Compatibilidad binaria**: ejecución de binarios `amd64` mediante Rosetta 2 en chips ARM.

### Limitaciones actuales

* No existe soporte para definir múltiples contenedores en conjunto, como ocurre con Docker Compose o Podman Compose.
* La herramienta de línea de comandos carece de algunas funciones avanzadas como visualización de registros, estadísticas o monitoreo de eventos.
* Las capacidades de red entre contenedores están limitadas en versiones anteriores a macOS 26 Tahoe, y podrían no funcionar en macOS Sonoma.

Ya se han iniciado discusiones en GitHub para añadir soporte para orquestación multicontenedor.

## Casos de uso prácticos

Desarrolladores ya han probado ejecutar contenedores individuales con distribuciones como Ubuntu y Alpine, integrando servicios como PostgreSQL y aplicaciones en Ruby on Rails. En pruebas realizadas sobre macOS 26 Tahoe, se demostró que los contenedores pueden conectarse entre sí, compartir volúmenes y ejecutar entornos completos de desarrollo aislados.

## conclusión

Este framework representa un cambio importante en la forma de ejecutar contenedores en macOS. Al ofrecer una solución oficial, nativa, segura y de alto rendimiento, Apple da un paso firme hacia la integración del desarrollo con tecnologías de virtualización modernas en su ecosistema.

## glosario técnico

* **Contenedor OCI**: formato estándar para empaquetar aplicaciones y sus dependencias en entornos Linux.
* **Micro‑VM**: máquina virtual ligera, utilizada para aislar cada contenedor de forma eficiente.
* **Virtualization.framework**: conjunto de herramientas de macOS para gestionar máquinas virtuales desde código nativo.
* **vminitd**: pequeño sistema de inicio escrito en Swift, encargado de iniciar procesos dentro de las micro‑VMs.
* **Rosetta 2**: tecnología de Apple que permite ejecutar aplicaciones desarrolladas para arquitecturas x86 en procesadores ARM.
* **macOS Sonoma / macOS 26 Tahoe**: versiones del sistema operativo de Apple; Tahoe es la más reciente, en beta.
* **Dockerfile / Compose**: herramientas utilizadas para construir imágenes y definir múltiples contenedores que trabajan en conjunto.

## fuentes

1. Apple Container Runtime Open Source en GitHub
   [https://github.com/apple/container](https://github.com/apple/container)
   Repositorio oficial de la herramienta de línea de comandos para ejecutar contenedores nativos en macOS.

2. Containerization Framework de Apple en GitHub
   [https://github.com/apple/containerization](https://github.com/apple/containerization)
   Librería en Swift que permite crear y gestionar contenedores de manera integrada con macOS.

3. Apple Containers on macOS - InfoQ
   [https://www.infoq.com/news/2025/06/apple-container-linux/](https://www.infoq.com/news/2025/06/apple-container-linux/)
   Artículo técnico que explica el funcionamiento del nuevo sistema de contenedores de Apple y lo compara con soluciones existentes.

4. Apple Containers - Medium
   [https://medium.com/@rpavank2000/apples-container-native-lightweight-container-runtime-for-macos-44a69d57ef41](https://medium.com/@rpavank2000/apples-container-native-lightweight-container-runtime-for-macos-44a69d57ef41)
   Análisis técnico de Containerization con ejemplos de uso.

5. Kali Linux en contenedores de Apple - BleepingComputer
   [https://www.bleepingcomputer.com/news/security/kali-linux-can-now-run-in-apple-containers-on-macos-systems/](https://www.bleepingcomputer.com/news/security/kali-linux-can-now-run-in-apple-containers-on-macos-systems/)
   Demostración del uso de contenedores de Apple para ejecutar distribuciones como Kali Linux.
