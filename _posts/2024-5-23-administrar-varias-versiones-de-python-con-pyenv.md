---
layout: post
title: Administrar varias versiones de Python con PyEnv
author: Ronny González
category: programacion
tags: [gestores-de-versiones, python]
excerpt: Aprende como administrar varias versiones de Python usando PyEnv y olvídate de tener varias versiones instaladas en tu sistema
---

## ¿Qué es PyEnv?

PyEnv es una herramienta que nos permite gestionar múltiples versiones de Python en un mismo sistema operativo, facilitando el cambio entre ellas y asegurando que nuestros proyectos utilicen la versión adecuada.

Imagina tener un proyecto que utilice versiones diferentes de Python a las actuales, o que tengan problemas de compatibilidad. Con esta herramienta, podrás evitar instalar varias versiones de Python en el sistema, ya que esto puede ser tedioso y generar conflictos.

## Información importante

Recomiendo personalmente desinstalar Cualquier versión de Python que tengamos instalada en nuestro sistema, o eliminarla de la variable de entorno path, ya que el sistema puede elegir esa versión y PyEnv no funcionará como esperamos.

## Instalación en Windows

Para instalar PyEnv en Windows, utilizaremos pyenv-win, hecha originalmente para linux, pero se le hizo un port para Windows.

1.  Debemos descargar la herramienta desde su repositorio de GitHub en el siguiente [enlace](https://github.com/pyenv-win/pyenv-win).
1.  Creamos un directorio y le llamaremos .pyenv en la carpeta personal _ La carpeta del usuario _. Descomprimimos la carpeta pyenv-win y el archivo .version justo en ese directorio
1.  Ahora, debemos agregar varias rutas a las variables de entorno, tanto en el path del usuario como en las variables de entorno principales. Para esto podemos hacerlo de manera manual y usando la terminal PowerShell. Lo haremos usando el segundo método.

    - Abre la terminal como administrador.
    - Ingresa lo siguiente:
    ```PowerShell
    [System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
    [System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
    ```

    Estas variables apuntan al directorio .pyenv que está en la carpeta personal.
    - Continuamos añadiendo dos variables más, pero esta vez en el path. Estas nos permitirán llamar a pyenv desde la terminal de PowerShell. Seguimos con la terminal abierta en administrador y ejecutamos lo siguiente:
    ```
    [System.Environment]::SetEnvironmentVariable('path', $env:USERPROFILE + "\.pyenv\pyenv-win\bin;" + $env:USERPROFILE + "\.pyenv\pyenv-win\shims;" + [System.Environment]::GetEnvironmentVariable('path', "User"),"User")
    ```
1.  Finalmente, cerramos la terminal que teníamos abierta en administrador y podemos abrir otra ventana de terminal normalmente.

## Instalar PyEnv en Mac

Para instalar PyEnv en Mac, usaremos Homebrew.

1. Si no tienes Homebrew instalado, abre la terminal y ejecuta:

    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

1. Puede que necesitemos instalar dependencias, ya que PyEnv compila desde el código fuente. Para ello, ejecutamos lo siguiente.

    ```
    brew install openssl readline sqlite3 xz zlib
    ```

1. Para instalar la herramienta usamos el siguiente comando:

    ```
    brew update
    brew install pyenv
    ```

1. Añade PyEnv al shell ejecutando:

    ```
    echo 'if command -v pyenv 1>/dev/null 2>&1; then eval "$(pyenv init --path)"; fi' >> ~/.zshrc
    echo 'if command -v pyenv 1>/dev/null 2>&1; then eval "$(pyenv init --path)"; fi' >> ~/.bash_profile
    ```

1. Reinicia tu terminal y cuando lo hagas ya podrías usar los comandos de pyenv

## Instalar PyEnv en Linux

Para instalar PyEnv en Linux, seguimos estos pasos:

Pero antes, también tenemos que instalar dependencias, por la misma razón que en mac. En El caso de Debian y Ubuntu, debemos ejecutar lo siguiente.

```bash
sudo apt update
sudo apt install build-essential libssl-dev zlib1g-dev libbz2-dev \ libreadline-dev libsqlite3-dev curl libncursesw5-dev xz-utils tk-dev libxml2-dev \ libxmlsec1-dev libffi-dev liblzma-dev
```

Para otras distros, debemos fijarnos en si Python da algún error he instalar las dependencias que nos pida.

1. Abre la terminal
1. Clona el repositorio de PyEnv:

    ```bash
    curl https://pyenv.run | bash
    ```

1. Añade PyEnv a tu shell y haz que se inicie de manera automática ejecutando:

    ```bash
    echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
    echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
    ```

Con esto, tendremos PyEnv funcionando en el sistema operativo de nuestra preferencia.

## Usando PyEnv

Como habníamos dicho en la introducción, esta herramienta nos permite administrar varias versiones de Python a la vez, pudiendo cambiarnos entre ellas sin ningún problema. También podremos establecer versiones para una carpeta en específico y de manera global.

Tengamos en cuenta que si usamos una versión para una carpeta, esta se aplicará también para las subcarpetas que se encuentran en ellas.

### Instalar una versión de Python

Para instalar una nueva versión de Python, usa el comando:

```
pyenv install <VersionPython>
```

VersiónPython quiere decir solo el nombre de la misma.

Por ejemplo, para instalar Python 3.10.8:

```
pyenv install 3.10.8
```

### Listar versiones de Python

Para ver las versiones de Python instaladas, ejecuta:

```
pyenv versions
```

### Ver la versión instalada globalmente o si estamos en un directorio que contiene una versión asignada

```
pyenv version
```

La versión que estamos usando se marca con un asterisco, ya sea en global o en local

### Establecer la versión global de Python

Para establecer una versión global de Python que se utilizará por defecto, en todo el sistema, usamos:

```
pyenv global <version>
```

Por ejemplo, Para establecer la versión 3.12.3, luego de instalarla ejecutamos

```
pyenv global 3.12.3
```

Con esto, la versión seleccionada será la que se usará por defecto cuando llamemos la consola intérprete de Python.

### Establecer la versión local de Python

Para establecer una versión de Python específica para un proyecto (en el directorio actual), ejecuta:

```
pyenv local <version>
```

Por ejemplo, Luego de instalar la versión 3.7.4 con el comando `pyenv install 3.7.4`, ejevutamos:

```
pyenv local 3.7.4
```

Con esto, sucederá lo explicado más arriba. Usando una versión en específico para un directorio, se aplicará a los demás directorio dentro de él, y la global seguirá siendo la misma que establecimos, sin generar algún conflicto.

## Actualizando PyEnv

Para actualizar la herramienta, lo hacemos con el comando `pyenv update`, Así estaremos al día con nuevas mejoras.

## Conclución

Ya para terminar, opino que la herramienta PyEnv es imprescindible para nuestro día a día como desarrolladores, ya que nos ayuda a administrar versiones de una forma fácil y sencilla.

También podemos añadirle plugins para ampliar las funcionalidades que nos brinda.

Comparto un enlace a la documentación odicial para aprender más.

[Documentación de PyEnv](https://github.com/pyenv/pyenv)

Con esto hemos llegado al final de este post y será hasta una próxima entrega. Su amigo y servidor Ronny Les manda un gran saludo.
