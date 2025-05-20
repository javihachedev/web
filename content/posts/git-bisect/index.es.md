+++
categories = ['Blog Técnico']
date = '2022-02-01T00:00:00+00:00'
draft = false
title = 'Encontrando el bug con git-bisect'
+++

Imagina que estás trabajando en un proyecto y un día te das cuenta de que algún componente ya no funciona. Los logs no dan ninguna pista sobre dónde está el problema. Hay tantas líneas de código para el componente que pasarías años depurándola. También es imposible identificar el error ejecutando pruebas. Pero hay un detalle importante, sabes que en la versión anterior el componente funcionaba bien. ¿Qué harías para identificar el código problemático?

Seguramente podrías dar varias respuestas a esta pregunta, pero hoy vamos a hablar sobre una operación de git que te ayudará a resolver este problema: `git bisect`

Usando el comando `git bisect` podremos identificar el commit exacto que introdujo el error en nuestro software. Bajo el capó, git bisect realizará una búsqueda binaria tomando como punto de partida una versión buena y una versión con fallos.

Como ejercicio práctico he creado un [repositorio en Github](https://github.com/frahergal/git_bisect_exercise) para seguir los siguientes pasos si quieres probar git bisect por ti mismo. No te preocupes, solo necesitas un terminal. El proyecto contiene solo un script bash que imprime si la versión está funcionando o si está fallando. De esa manera vamos a simular un caso real.

> 🖼️ Insectos, mariposas y un saltamontes. 1664. Jan van Kessel
