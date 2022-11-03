---
title: Programar, lo que nadie te dice
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

> Programar se siente como hacer magia

### Ventajas de programar, pero sobre todo de analizar datos programando

- Nos entrega mucha mayor versatilidad y control que usar aplicaciones con GUI (interfases gráficas de usuario, por sus siglas en inglés). Quizás al comienzo no es tan intuitivo como arrastrar iconos por la pantalla, pero es mucho más poderoso. 
- Te permite utilizar los recuros de tu computador de manera más eficiente. Todo esos gráficos utilizan memoria que vas a querer usar mejor en tu análisis. Hay un límite máximo para tus filas en Excel, si tienes más datos que eso, aunque tengas memoria disponible, solo te queda trabajar programando.
- Tienes un registro. Cada paso en tu análisis es un comando en tu script. Lo que te permite corregir errores o hacer modificaciones fácilmente.
- Es repetible, lo que no solo es bueno para la transparencia de tu análisis y mantener los principios científicos, sino que además te permite automatizar el proceso o reciclar pasos para un nuevo análisis.
- Es muy rápido para trabajar con muchos datos y tareas en lote.
- Evitas introducir errores manipulando la fuente de datos directamente.
- Es gratis! La gran mayoría de los lenguajes de programación son gratuitos y de código abierto, así también ocurre con gran parte de herramientas adicionales. No hay necesidad de pagar por costo software especializado.

### Desventajas de programar:

- Require aprender. La curva de aprendizaje es un costo a considerar, además hay que mantenerse actualizado.
- Consume tiempo. A veces para un análisis rápido las herramientas con GUI son mucho mejores. Y si bien es más fácil corregir errores, también es fácil cometerlos ya que todas las instrucciones son escritas en un lenguaje no ambigüo, un error de tipeo puede arruinar toda la operación
- Puede ser difícil corregir un error único en los datos, versus la alternativa manual.

Este post no apunta a enseñarte a cómo programar (o solo un poco). Para eso hay un montón de cursos gratis y pagados (ver lista de recursos recomendados al final del post). En cambio, este texto te va a explicar lo que ninguno de esos cursos te enseña (y para mí fue un problema al comenzar a programar), a través de una mezcla entre conceptos básicos y tutorial.


## Qué es un lenguaje de programación

Un lenguaje de programación, como cualquier otro lenguaje, es una serie de convenciones de como ordenar palabras para darle intrucciones al computador.

Digamos que es una forma a mitad de camino entre el lenguaje de las máquinas (de ceros y unos, como puedes ver en [el artículo Arquitectura de computadores](#)) y el lenguaje humano.

Estas instrucciones son compiladas por un programa llamado `interprete`, que traduce tu programa o texto en instrucciones para la máquina.

En la práctica esto ocurre en dos procesos. El código debe compilarse (traducirse de texto a bytes) y luego ejecutarse (el computador sigue la instrucciones). Algunos lenguajes exigen al usuario hacer ambos pasos por separado (e.g. Java), mientras que otros se compilan al tiempo de la ejecución (Python o Javascript)
{: .notice}

Los lenguajes de programación suelen clasificarse en un continuo que va de **bajo nivel**, cuando el lenguaje es más cercano al de las máquinas (como FORTRAN o C), hasta de **alto nivel** cuando el lenguaje es más cercano a los humanos (como Python o Go). Normalmente los lenguajes de bajo nivel son más difíciles para programar, pero mucho más rápidos al ejecutarse, mientras que los de alto nivel son lentos, pero mucho más fáciles de aprende y usar.

Otras diferencias entre lenguajes de programación según diferentes funcionalidades, especialisaciones y sobre todo, gustos. Aunque no es importante saber eso por ahora.
{: .notice}

Una diferencia importante con un lenguaje natural (como el español), es que el de programación no tiene espacio para `ambigüedades`. Por ejemplo la frase:

"El viejo miró al niño con un telescopio"🐻
{: .notice}

Esta frase es ambigüa ya que puede interpretarse como que un viejo miró a un niño usando un telescopio o que el niño tenía un telescopio.

Un computador no podría discernir entre ambas. En el mejor de los casos escogería una interpretación y la ejecutaría de manera consitente (escogería la misma interpretación siempre), en el peor (el más común), el programa se negaría a interpretarlo y nos devolvería en letras rojas un error en la ejecución.

## Un script, un IDE, una distribución

Programar es entonces escribir texto usando las convensiones de un lenguaje en particular. Un `script` es este archivo de texto. Ese archivo se puede escribir en blog de notas, o cualquier otro procesador de texto.

Hay procesadores de texto especialemente diseñados para programar, que te ayudan a seguir las convenciones del lenguaje que vas a utilizar e incluso te autocompletan o sugieren texto, así como señalar posibles errores. Además hay programas especializados para escribir, compilar y ejecutar tus script, así como ayudarte a detectar errores (o bugs). Estos últimos se llaman IDE´s.

Ademas del procesador de texto y el interprete,  muchas veces se se empaquetan todas estas cosas en una distribución. Por ejemplo, en los tutoriales usaremos Python, que puedes descargar en su versión vainilla [página aquí](#) o puedes instalar una distribución diferente llamada Anaconda, que además instalara IDEs, entornos de ejecución y las librerías más comunes para análisis de datos. Recomiendo bajar esta [versión aquí](#).

## Comencemos a programar - Mini tutoriales (sin necesidad de instalar nada)

### Hackeando el lado oscuro del computador

La mayoría de los computadores ya cuentan con interpretes instalados. Sin ir más lejos el navegador en que estas leyendo este texto esta interpretando un lenguaje de marcado (HTML), de estilo (CSS) y de programación (Javascript). Juguemos con este último.

Si estas usando Chrome para ver esta página, has click con el botón derecho del ratón en el cualquier parte del sitio. Del menú que se despliega has click en `inspecionar`. Ahora se abrirá una sub-ventana que te mostrará la estructura del sitio en HTML. 

![Consola](/assets/images/primer script1.png)

Ahora, en la sub-ventana, dale click a la pestaña que dice `Consola`. Ahí veras un simbolo ">" y una línea parpadeante lista para recibir instrucciones.

Escribe la instrucción:

```Javascript

alert("Hola mundo");

```
Reemplaza "Hola mundo" por lo que quieras escribir (Hola mundo es tradicionalemente el primer programa de todo programador, pero yo te ofrezco la libertad creativa). Recuerda conservar las comillas y el punto y coma al final de la línea.

Dale enter y ve que ocurre.

Ok, spoiler alert. Una nueva ventana mostrando tu mensaje se ha abierto. Dale Ok para cerrar y ya está. Has ejecutado tu primera línea de código en Javascript.

Este codigo se ha ejecutado localmente, es decir, solo para ti, no has hackeado la pagina web. Sin embargo, no es muy distinto a lo que se hacia para hackear en los primero anos de internet donde era facil escribir codigo en un foro en vez de escribir un comentario, es codigo se ejecutaba en cada computador que visitaba esa pagina.{: .notice}

### Automatizando tu trabajo

Si tu máquina es Windows además puedes ejecutar PowerShell para programar tu computador (como automatizar tareas repetitivas). Si en cambio estas utilizando Linux o Mac, puedes abrir la `teminal` y ejecutar Bash sin que tener que instalar nada adicional para hacer lo mismo.

Hagamos la prueba. Si estas usando Windows 10 o superior,  Presiona las teclas `q` + `tecla de Windows` (entre Ctl y Alt) o has click en la lupa en la barra de tareas y busca "Powershell".

Una terminal de fondo azulado se abrirá. La terminal es muy útil sino la has usado antes. Te permite copiar archivos, crear carpetas incluso conectarte a internet a través de comandos. En Windows también puede hacer eso a través del cmd (command display), pero este no soporta scripts.

Nuestro objetivo es crear una serie de carpetas y copiar un archivo dentro de ellas. Esta tarea puede tomar mucho tiempo si lo tenemos que hacer manualmente, asi que vale la pena que lo hagamos programando.

Lo primero que haremos será ejecutar un comando para cambiar de carpeta. Por defecto PowerShell inicia en la capeta de usuario, debemos cambiar a la carpeta de "Documentos". Para ello escribe:

```
cd Documentos
```
cd es un comando que significa `c`hange `d`irectory (cambiar directorio en ingles), y luego le damos el nombre de la capeta que queremos abrir dentro del directorio que estamos actualmente. (Si queremos volver a la carpeta anterior solo debemos escribir `cd ..`)

Si queremos saber que carpetas hay en nuestra nueva ubicación, podemos ejecutar el comando `dir`. La terminal nos entregara una lista de las carpetas y archivos.

El siguiente paso es crear una carpeta donde vamos a trabajar. Para ello escribe:

```
mkdir pwtutorial
```

Ejecuta el comando `dir` para segurarnos que la carpeta fue creada y luego entra a la carpeta en ella:

```
cd pwtutorial
```

Una vez aquí podemos crear un archivo de texto para eso vamos a escribir un texto (siempre entre comillas, para que el computador sepa que es un texto y no un comando) y luego lo vamos a sacar (output) con el signo ">" hacia un archivo de texto que llamaremos 'test' (puedes copiar y pegar en tu PowerShell este comando, solo ten en consideración que en futuro nunca correr o copiar comandos o un script que no entiendas):

```
"Este es mi primer archivo" > test.txt
```

Busca la carpeta en tu computador como lo harías regularmente en el explorador de Windows, y comprueba que el contenido esté ahí.

El último paso antes de comenzar con la magia es copiar el archivo de texto a la nueva carpeta. Para eso crearemos una nueva carpeta "carpeta1"  y usamos el comando `cp "archivo a copiar" "carpeta de destino"`.

```
cp test.txt carpeta1
```
Ya sabemos como cambiar, crear y copiar carpetas y archivos. Es hora de automatizarlo. 

Crearemos 20 carpetas y copiaremos nuestro archivo dentro de ellas. Usando un `loop`, un repetidor. 

El loop `for` es común a muchos lenguajes de programación, se puede traducir como "Por cada vuelta has esto ...". Para usarlo primero llamamos a `for`, luego pasamos entre paréntesis un contador. Creamos una variable (es decir una entidad cuyo valor va a cambiar, variar) usando el signo `$` y un nombre, en nuestro caso lo llamaremos `contador`. Como ya creamos la carpeta "1", iniciaremos nuestro $contador en 2. En una segunda operación definiremos una condición que de ser verdadera, el loop ejecutará una vuelta. En nuestro caso que el sea $contador menor o igual (-le, por less or equal) a 20. Finalmente le diremos a nuestro $contador que se modifique a sí mismo en cada vuelta y aumente su valor en 1. Hay varias formas de hacer eso, pero la mas breve es diciendo `$contador++`.

Luego que el contador está definido podemos abrir llaves para decir que tareas queremos que se ejecuten cada vez que el contador cambie. La primera será definir el nombre de la carpeta. Ya que ocuparemos este nombre más de una vez, vale la pena guardarlo en una variable, la llamaremos `$nombreCarpeta` y le asignaremos la palabra "carpeta" concatenando (sumar dos textos produce que estos se junten) con el valor del $contador. Luego crearemos la carpeta con el $nombreCarpeta y luego copiaremos el archivo a la carpeta. Nota que como el valor del $contador es diferente en cada repetición, por lo que el $nombreCarpeta será diferente.

Si ponemos todo junto nos queda la siguiente operación:

```
for ($contador=2;$contador -le 20;$contador++){$nombreCarpeta="carpeta"+$contador; mkdir $nombreCarpeta; cp test.txt $nombreCarpeta}
```
Ejecutamos y ya está, trabajo hecho. Lo mejor es que si queremos hacerlo por 100 carpetas no hay diferencia, solo cambiamos el número máximo de nuestro contador. También podemos introducir nuevas variables o crear/modificar el archivo de texto para que tenga contenido diferente. Podríamos incluso usar comandos para extraer al fecha actual y nombrar nuestros archivos usando la fecha, etc, etc.

El último paso es convertir ese comando en una script que podemos reutilizar desde cualquier carpeta. Para ello crea un archivo de texto, usando PowerShell o cualquier otro método, copia el loop que definimos arriba y guardalo con una terminación ".ps1". Para ejecutar tu script has click con el botón derecho del ratón y selecciona la opción "Correr con Powershell".

[Si quieres saber que más puede hacer Powershell cliquea aquí](#)

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

Ahora que ya sabemos estos conceptos te puede ser más fácil embarcarse en algunos de estos recursos.

🚩Advertencia: Varios de los mejores recursos están en inglés. Y esto es importante. A pesar de que los hablantes de español somos casi el 8% de los usuarios de internet, solo un 4% de las páginas está en español (por lo que este blog es una humilde contribución a ese espacio), mientras que un 60% esta en inglés. Saber inglés no solo es útil para programar, también te da acceso a un montón de tutoriales e información. El cyber espacio es al menos 15 veces más grande en inglés, es más probable que encuentres lo que buscas.
{: .notice--danger}

- [Coursera](#)
- [Udemy](#)
- [Free Code Camp](https://www.freecodecamp.org/espanol/)
- [Project Odin](https://www.theodinproject.com/paths)
- [Piensa Python (libro)](https://argentinaenpython.com/quiero-aprender-python/aprenda-a-pensar-como-un-programador-con-python.pdf)
- [Python Programming. Tutoriales de todo en Python](https://pythonprogramming.net/)

