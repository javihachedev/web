+++
categories = ['Blog Técnico']
date = '2022-01-18T20:46:21+02:00'
draft = false
title = 'Antipatrón: lava seca'
+++

Hoy me gustaría hablaros del antipatrón "Lava seca" (o "Lava flow"/"Dead code" en inglés). Un antipatrón que desafortunadamente me he encontrado en algunos proyectos en los que he trabajado.

![Imagen de presentación con el icono de un volcán y el texto Lava flow antipattern](imgs/lava_flow_antipattern_card.png)

Este antipatrón suele darse lugar en proyectos que son creados inicialmente como un prototipo, un software de investigación o como parte de un hackaton pero que posteriormente se convierte en un software operacional y es llevado a producción.

La razón detrás del nombre "Lava Seca" es simple. Inicialmente el software es desarrollado con una documentación muy vaga o inexistente, intentando varias soluciones para implementar las funciones del programa, bien sea por tener un tiempo muy limitado o porque los programadores se ponen a probar distintas formas de llegar a una solución. Ese código inicial que forma parte de las primeras versiones acaba siendo arrastrado y cuando llega el momento de refactorizarlo es demasiado tarde. La deuda técnica que se acumula es tan inmensa que nadie en el equipo sabe si una refactorización puede producir más problemas que otra cosa.

Este antipatrón se hace incluso más evidente cuando los programadores que comenzaron el proyecto ya no forman parte de él. Si no has tenido que pasar por ello, imagina lo que es hacer ingeniería inversa de un proyecto con miles de líneas, pobremente documentadas y lleno de código spaghetti.

La solución a este antipatrón una vez que está presente en el código es bastante compleja. Sin duda alguna la mejor sería revisar, documentar y reemplazar el código inservible en la mayor medida de lo posible. Pero como normalmente no se dispone de un tiempo ilimitado para hacerlo, hay algunas herramientas (por ejemplo Sonarqube) que nos pueden ayudar a hacer análisis estáticos de código de forma automática. De esta forma al menos podremos identificar los puntos más críticos y dar prioridad a esos cambios.

Para evitar que esto no acabe ocurriendo en nuestros proyectos hay que intentar documentar siempre el código desde el inicio del proyecto y mantenerlo relativamente "limpio". Incluso si es un proyecto que haces para probar algo o como hobby. Nunca sabes si en un futuro lo vas a utilizar para hacer algo más complejo.

> 🖼️ La erupción del Vesuvio. 1771. Pierre-Jacques Volaire. 