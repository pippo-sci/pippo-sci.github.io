---
title: Arquitectura de Computadores
excerpt_separator: "<!--more-->"
categories:
  - Conceptos Básicos
tags:
  - Computo
---

> Conoce a tu enemigo

¿Cómo es que una máquina que solo entiende electricidad puede reproducir música, calcular rutas o reconocer tu cara? La respuesta está en varias capas de abstracción. Vamos a pelarlas de afuera hacia adentro: primero lo que ya conocés, luego de qué está hecho, después cómo funciona a nivel físico, y finalmente qué puede y qué no puede hacer.

## Las partes de un computador

Un computador tiene cuatro componentes fundamentales que interactúan entre sí:

- **CPU** (*Central Processing Unit*): el procesador. Es el cerebro. Ejecuta instrucciones —sumas, comparaciones, accesos a memoria— a velocidades de miles de millones de operaciones por segundo. 

- **GPU** Originalmente los procesadores ejecutaban instrucciones de a una (**serialmente**). Hoy los procesadores tienen múltiples núcleos que trabajan simultáneamente (**paralelo**). Las GPUs llevan esto al extremo con miles de núcleos pequeños especializados en tareas masivamente paralelas, como renderizar gráficos o entrenar modelos de inteligencia artificial.

- **Memoria** RAM (*Random Access Memory*): almacenamiento temporal y rápido. Es donde viven los datos y el programa mientras se ejecuta. Piénsala como el escritorio de trabajo: accesible al instante, pero se vacía al apagar el computador. O más bien como la memoria a corto plazo.
- **Almacenamiento** (disco duro HDD o SSD): almacenamiento permanente. Más lento que la RAM, pero persiste aunque se apague el equipo y tiene mucha mayor capacidad. Es el cajón o archivador. O la memoria a largo plazo.


Bien. Sabemos qué son las partes. Ahora la pregunta es: ¿de qué están hechas?

## Circuitos integrados y la tómbola de los procesadores

### Qué es un circuito integrado

Un **circuito integrado** (o *chip*) es una pequeña oblea de silicio sobre la cual se graban millones —hoy miles de millones— de `transistores`. Un transistor es básicamente un interruptor electrónico: puede estar abierto (sin corriente, `0`) o cerrado (con corriente, `1`). La magia está en que se pueden fabricar en tamaños increíblemente pequeños, todos a la vez, sobre el mismo trozo de material.

¿Por qué silicio? Porque es un **semiconductor**: a diferencia de un conductor como el cobre (que siempre deja pasar corriente) o un aislante como el plástico (que nunca la deja pasar), el silicio puede controlarse con precisión para hacer ambas cosas. Al "dopar" el silicio con pequeñas cantidades de otras sustancias se crean zonas con exceso o falta de electrones, que son la base de los transistores.

### El proceso de fabricación

Fabricar un chip moderno es uno de los procesos industriales más complejos que existen. Se realiza mediante **litografía**: una fuente de luz ultravioleta (o luz extremo ultravioleta, EUV) proyecta el patrón del circuito sobre una oblea de silicio cubierta con un material fotosensible. Luego se graban y eliminan capas selectivamente, como si se revelara una fotografía, hasta construir los transistores en tres dimensiones.

El tamaño de los transistores se mide en nanómetros (nm). Los chips más avanzados actuales tienen transistores de 3 nm, unas veinte veces más pequeños que un virus. A menor tamaño, más transistores caben en el mismo espacio, lo que se traduce en más velocidad y menor consumo de energía.

Durante décadas la industria siguió la **Ley de Moore**: el número de transistores en un chip se duplica aproximadamente cada dos años. Sin embargo, los límites físicos de la miniaturización hacen cada vez más difícil mantener ese ritmo.

Todo esto hace que el negocio de los chips se parezca un poco a una **tómbola**. Diseñar y fabricar un chip de última generación cuesta miles de millones de dólares, y solo unas pocas empresas en el mundo (TSMC, Samsung, Intel) tienen la capacidad de producirlos. El proceso tiene tasas de defecto no despreciables: de una misma oblea se cortan cientos de chips, y los que tienen defectos se descartan o se venden como versiones de menor rendimiento. Por eso dos procesadores del mismo modelo pueden tener rendimientos distintos, y los entusiastas del *overclocking* aprovechan que muchos chips son en realidad versiones de mayor rendimiento vendidas a menor precio porque no dieron el ancho en los tests de control de calidad.

Ya sabemos que los chips están hechos de transistores. Pero ¿cómo hace un interruptor de electricidad para representar letras, números o imágenes?

## Ceros y unos

Toda la información dentro de un computador se representa como secuencias de ceros y unos. Pero ¿por qué específicamente dos estados? ¿Por qué no tres, o diez? La respuesta está en una combinación de física y matemática.

### Electrónica

Un circuito electrónico puede estar en dos estados estables: con corriente pasando o sin corriente. Para hacerlo robusto al ruido, se definen **umbrales de voltaje**: por encima de cierto nivel es un `1`, por debajo es un `0`. Aunque el voltaje varíe un poco, mientras esté por encima del umbral sigue siendo un `1`. Es como comparar un semáforo (rojo o verde, sin ambigüedades) con un gradiente de color: la discreción hace al sistema mucho más tolerante a las imperfecciones físicas.

Los **circuitos lógicos** combinan estas señales para hacer operaciones. Las **compuertas lógicas** (AND, OR, NOT y sus variantes) son los ladrillos básicos: cada una toma uno o más bits de entrada y produce un bit de salida según reglas fijas. Combinando miles de estas compuertas se construyen circuitos capaces de sumar, comparar, almacenar y tomar decisiones. Combinando millones de esos circuitos, nace un procesador.

### Teoría de la información

Sabemos cómo se representa un bit en el hardware. Pero ¿por qué binario tiene sentido matemáticamente? En 1948, el ingeniero Claude Shannon publicó un paper que fundó la **Teoría de la Información** y respondió exactamente esa pregunta.

Shannon definió la **entropía** de una **fuente** de información como una medida de su incertidumbre. Piénsalo así: si alguien te dice el resultado de lanzar una moneda normal, eso te aporta información, podía haber caído de dos formas. Pero si la moneda está trucada y siempre cae cara, el mensaje no te dice nada nuevo. A mayor incertidumbre de la fuente, mayor es la información que transmite cada mensaje. La **ganancia de información** (*information gain*) mide exactamente cuánto aprendemos al conocer el resultado.

De aquí surge el **bit** (*binary digit*): la mínima cantidad de información, equivalente a la respuesta a una pregunta de sí/no. Toda la información —texto, imagen, sonido, video— puede codificarse como una cadena de bits. Binario no es una limitación del hardware: es el sistema más simple posible para representar cualquier cantidad de información.

Pero la información no existe en el vacío: se transmite a través de un **canal**. Puede ser un cable, el aire, una fibra óptica o incluso un DVD. Todo canal introduce **ruido** que puede corromper el **mensaje**. Shannon demostró que existe un límite teórico a cuánta información puede transmitirse por un canal con determinado nivel de ruido: la **capacidad del canal**. Superar ese límite es matemáticamente imposible.

El problema práctico es entonces cómo **codificar** la información para transmitirla eficientemente, y qué hacer cuando el ruido la corrompe. Para eso el **receptor** necesita mecanismos de **detección de errores** (saber que algo llegó mal) y **corrección de errores** (reconstruir el mensaje original). El dígito verificador del RUT o el ISBN de un libro son ejemplos simples: un número extra que permite detectar un error de tipeo. Los discos duros, el streaming de video y las comunicaciones satelitales usan técnicas mucho más sofisticadas basadas en los mismos principios.

## Memoria o almacenamiento: ¿Cuál es la diferencia?

Son dos cosas distintas que se confunden frecuentemente, en parte porque en el lenguaje cotidiano usamos "memoria" para las dos.

La **memoria** (RAM) es como el escritorio de trabajo: rápida y accesible al instante, pero con espacio limitado y que se borra al apagar el computador. Cuando abres un programa, el sistema operativo lo carga desde el disco al escritorio (RAM) para trabajar con él.

El **almacenamiento** (disco duro HDD o SSD) es como el cajón o el archivador: más lento para acceder, pero persiste aunque se apague el computador y tiene mucha más capacidad.

La diferencia de velocidad es enorme. Un SSD moderno puede leer datos a ~5.000 MB/s, la RAM transfiere a ~50.000 MB/s, y los registros internos del procesador son más rápidos aún. Por eso existe una **jerarquía de memoria**:

> Registros (rapidísimos, poquísima capacidad) → Caché → RAM → SSD → HDD (más lento, mucha capacidad)

Cada nivel es más lento pero más barato y abundante que el anterior. El procesador trabaja principalmente con los registros, pero cuando necesita un dato que no está ahí, lo busca en el siguiente nivel, y así sucesivamente.

Cuando el programa en ejecución necesita más RAM de la disponible, el sistema operativo puede usar parte del disco como RAM extra —lo que se llama **memoria virtual** o *swap*. Como el disco es órdenes de magnitud más lento, esto hace que el computador se sienta pesado e irresponsivo.

## Poder de cómputo

[Los límites de la computación](#)

No todo lo que puedes imaginar puede ser calculado por un computador, y no todo lo que puede calcularse puede hacerse en un tiempo razonable.

### Problemas computables

Un problema es **computable** si existe un algoritmo que lo resuelve en un número finito de pasos. La mayoría de los problemas cotidianos lo son: ordenar una lista, comprimir una imagen, buscar una palabra en un texto.

Pero "computable" no equivale a "rápido". Los científicos clasifican los problemas según cómo crece el tiempo de resolución al aumentar el tamaño de la entrada. Los problemas en clase **P** escalan razonablemente: duplicar el tamaño del problema no mucho más que duplica el tiempo. Los de clase **NP** escalan exponencialmente: agregar un elemento más puede doblar el tiempo necesario.

Un ejemplo clásico de problema difícil es el **problema del viajante**: dado un mapa con N ciudades, ¿cuál es la ruta más corta que las visita todas? Para 10 ciudades es manejable, pero para 100 el número de rutas posibles supera la cantidad de átomos en el universo observable. Los computadores más rápidos del mundo no pueden resolverlo de forma exacta en ningún tiempo útil.

### Problemas no computables

Más sorprendente aún: hay problemas que **ningún computador puede resolver**, sin importar cuánto tiempo o memoria tenga.

El más famoso es el **problema de la parada** (*halting problem*), demostrado por Alan Turing en 1936: no existe ningún programa capaz de determinar, para cualquier programa arbitrario, si ese programa terminará de ejecutarse o correrá para siempre.

La demostración es elegante: supone que ese programa existe y construye un caso que lo contradice lógicamente, similar a la paradoja del barbero que afeita a todos los que no se afeitan a sí mismos —una contradicción inevitable.

Esto no es una limitación tecnológica que se resuelva con más potencia de cómputo. Es una limitación matemática fundamental. Turing demostró que cualquier computador universal tiene estos límites inherentes, independientemente de su velocidad o tamaño.

## Bibliografía

[1] Patterson, D. A. & Hennessy, J. L. (2017). Computer Organization and Design. Morgan Kaufmann.

[2] Sipser, M. (2012). Introduction to the Theory of Computation. Cengage.