---
title: Programar, lo que nadie te cuenta
excerpt_separator: "<!--more-->"
categories:
  - Conceptos Básicos
  - Tutorial
tags:
  - Programación
---

Si estas leyendo este blog posiblemente ya sabes cómo usa un computador y navegar por internet (daAh!😜), pero sino sabes programar posiblemente aun no has liberado todo el potencial de la máquina que tienes enfrente.

La mayoría de la gente interactua con un computador a través de programas o software que empresas o programadores crean y que les permiten aprovechar las ventajas de su computador sin saber tanto al respecto, muchas veces incluyendo bellas interfaces de usuario para hacer más ~~adictiva~~ placentera la experiencia.

Sin embargo, programar te abre una ventana directa a aprovechar el poder computacional por tí mismo, y si eres suficientemente creativo, tu únicos límites serán los de las [leyes computacionales](#).

> Programar se siente como tener super poderes

Ahora, este post no apunta a enseñarte a cómo programar. Para eso hay un montón de cursos gratis y pagados (ver lista de recursos recomendados al final del post). Sino, este texto te va a explicar lo que ninguno de esos cursos te enseña (y para mí fue un problema al comenzar a programar), a través de una mezcla entre conceptos básicos y tutorial.

## Qué es lenguaje de programación

Un lenguaje de programación, como cualquier otro lenguaje, es una serie de convenciones de como ordenar palabras para darle intrucciones al computador.

Digamos que es una forma a mitad de camino entre el lenguaje de las máquinas (de ceros y unos como puedes ver en [el artículo Arquitectura de computadores](#)) y el lenguaje humano.

Estas instrucciones son compiladas por un programa llamado `interprete`, que traduce tu programa o texto en instrucciones para la máquina.

En la práctica esto ocurre en dos procesos. El código debe compilarse (traducirse de texto a bytes) y luego ejecutarse (el computador sigue la instrucciones). Algunos lenguajes exigen al usuario hacer ambos pasos por separado (e.g. Java), mientras que otros se compilan al tiempo de la ejecución (Python o Javascript)
{: .notice}

Los lenguajes de programación suelen clasificarse en un continuo que va de **bajo nivel**, cuando el lenguaje es más cercano al de las máquinas (como FORTRAN o C), hasta de **alto nivel** cuando el lenguaje es más cercano a los humanos (como Python o Go). Normalmente los lenguajes de bajo nivel son más difíciles para programar, pero mucho más rápidos al ejecutarse, mientras que los de alto nivel son lentos, pero mucho más fáciles de aprende y usar.

Otras diferencias entre lenguajes de programación tiene que ver con la orientación que tienen. Algunos son usados para programar para el firmware de electrónicos (C), otros para aplicaciones de celular (Kotlin), o gráficos 3D (C#). Algunos son Orientados a objetos, otros orientados eventos. Algunos son funcionales otros son imperativos. Pero no es importante saber eso por ahora.
{: .notice}

Una diferencia importante con un lenguaje natural (como el español), es que el de programación no tiene espacio para `ambigüedades`. Por ejemplo la frase:

"El viejo miró al niño con un telescopio"🐻
{: .notice}

Esta frase es ambigua ya que puede interpretarse como que un viejo miró a un niño usando un telescopio o que el niño tenía un telescopio.

Un computador no podría discernir entre ambas. En el mejor de los casos escogería una interpretación y la ejecutaría de manera consitente (escogería la misma interpretación siempre), en el peor (el más común), el programa se negaría a interpretarlo y nos devolvería en letras rojas un error en la ejecución.

## Un script, un IDE, una distribución

Programar es entonces escribir texto usando las convensiones de un lenguaje en particular. Un `script` es este archivo de texto. Ese archivo se puede escribir en blog de notas, Word o cualquier otro procesador de texto.

Hay procesadores de texto especialemente diseñados para programar, que te ayudan a seguir las convenciones del lenguaje que vas a utilizar e incluso te autocompletan o sugieren texto, así como posibles errores. Además hay programas especializados para escribir, compilar y ejecutar tus script, así como ayudarte a detectar errores (o bugs). Estos últimos se llaman IDE´s.

Ya vimos que para programar basta con algun editor de texto. Pero además de eso necesitamos instalar un interprete del lenguaje que vamos a utilizar. Muchas veces hay más de una versión que puede incluir uno o más IDE u otras cosas, a eso le llamamos una distribución. Por ejemplo, en los tutoriales usaremos Python, que puedes descargar directamente de su [página aquí](#).

O puedes installar una distribución diferente llamada Anaconda, que además instalara IDEs, entornos de ejecución y las librerías más comunes para análisis de datos. Recomiendo bajar esta  [versión aquí](#).

## Comencemos a programar

Sin embargo, la mayoría de los computadores ya cuentan con interpretes instalados. Sin ir más lejos el navegador en que estas leyendo este texto esta interpretando un lenguaje de marcado (HTML), de estilo (CSS) y de programación (Javascript). Juguemos con este último.

Si estas usando Chrome para ver esta página, has click con el botón derecho del ratón en el cualquier parte del sitio. Del menú que se despliega has click en `inspecionar`. Ahora se abrira una sub-ventana que te mostrará la estructura del sitio en HTML. 

![Consola]("\assets\images\primer script1.png")

Ahora, en la sub-ventana, dale click a la pestaña que dice `Consola`. Ahí veras un simbolo ">" y una línea parpadeante lista para recibir instrucciones.

Escribe la instrucción:
```Javascript
alert("Hola mundo");
```
Reemplaza "Hola mundo" por lo que quieras escribir (Hola mundo es el primer programa tradicional de todo programador, pero yo te ofrezco en cambio la libertad). Recuerda consevar las comillas y el punto y coma al final de la línea.

Dale enter y ve que ocurre.

Ok, spoiler alert. Una nueva ventana mostrando tu mensaje se ha abierto. Dale Ok para cerrar y ya está. Tu primera línea de código en Javascript.

Si tu maquina es Windows además puedes ejecutar PowerShell para programar tu computador (como automatizar tareas repetitivas). Si en cambio estas utilizando Linux, puedes la Teminal Bash sin que tener que installar nada adicional para hacer lo mismo.

## Librerías, repositorios y la documentación

Una parte muy importante de los lenguajes de programación, es que tienen funcionalidades estandar para ahorrarnos tiempo. Además estas funcionalidades se pueden extender mediante el uso de `librerías`. Las librerías no es más que código escrito por otros sobre el que tu puedes trabajar para crear tu propia funcionalidades.

> Considera que si tu programa utiliza una librería estas creando una dependencia. Eso significa que quien quiera utilizar tu programa deberá instalar esa dependencia también para que esta funcione. 

Alguna vez tuve que mezclar la tecnología de un navegador web, con las funcionalidades de Photoshop y de un scanner para completar la información de una tabla y crear un archivo de Excel. Cada una de estas funcionalidades estaba en librerías diferentes que pude mezclar en un solo script. Eso se sintió muy poderozo.

> Un elemento central a la filosofía de programar es no repetirse a uno mismo, ni reescribir código que ya está escrito. Por eso se dice que construimos sobre el trabajo de otros.

Para conservar todo este código de manera ordenada es que existen `repositorios` de donde se pueden descargar e installar librerías de manera segura. Por ejemplo Python utiliza la librería PIP para baja otras librerías. Si usas Conda o Anaconda el comando `conda install nombre-libreria` te permite descargarlas de manera igual de fácil.

No todos tenemos una memoria infinita (Lee más al respecto en el artículo de [Las leyes (y límites) de la computación](#)) para recordar los detalles de cada funcionalidad y sus requerimientos, así que lo programadores están constantemente revisando la documentación de los lenguajes de programación o de las librerías que utilizan.

Cuando recién estaba aprendiendo, muchos tutoriales y cursos te enseñan un par de estas funcionalides sin explicarte de donde salen o mostrarle la lista de todas las opciones y eso era muy frustrante.

Es igual de importante, si creas tu propio código, documentar su funcionamiento para que otros puedan utilizarlo y entenderlo.

## Cómo programar

Ahora que ya sabemos estos conceptos les puede ser más fácil embarcarse en algunos de estos recursos.

🚩Advertencia: Varios de los mejores recursos están en inglés. Y esto es importante. A pesar de que los hablastes de español somos casi el 8% de los usuarios de internet, solo un 4% de las páginas está en español (por lo que este blog es una humilde contribución a ese espacio), mientras que un 60% esta en inglés. Saber inglés no solo es útil para programar, también te da acceso a un montón de tutoriales e información. El cyber espacio es al menos 15 veces más grande en inglés, es más probable que encuentres lo que buscas.
{: .notice--danger}

- [Coursera](#)
- [Udemy](#)
- [Free Code Camp](https://www.freecodecamp.org/espanol/)
- [Project Odin](https://www.theodinproject.com/paths)
- [Piensa Python (libro)](https://argentinaenpython.com/quiero-aprender-python/aprenda-a-pensar-como-un-programador-con-python.pdf)
- [Python Programming. Tutoriales de todo en Python](https://pythonprogramming.net/)

