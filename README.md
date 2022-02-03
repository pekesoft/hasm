# hasm
## Motivación
Human Assembler ha sido creado para establecer una capa de abstracción a bajo nivel de los lenguajes ensambladores de los distintos procesadores, microcontroladores, unidades de coma flotante, y toda clase de dispositivos capaces de computar para un propósito general.

Durante años y décadas han estado regidos por un código muy primitivo y poco evolucionado basado en mnemónicos y opcodes. El objetivo es llegar a la esencia de esos opcodes para crear un lenguaje dinámico, expresivo, fácil de aprender y de mantener, además de ser totalmente personalizable.

Esos mnemónicos al estar sujetos por los derechos del copyright eran distintos para cada fabricante, por lo que aprender un lenguaje ensamblador en concreto implicaba limitarse no sólo a las especificaciones de dicho procesador, si no también a su implementación del desarrollo de su arquitectura, con palabras claves exclusivas que nada se parecen a las de la competencia.

Eso de cara a la industria, a la educación, al mantenimiento y al desarrollo es un handicap mayúsculo, ya que es necesario aprenderse las peculiaridades de cada lenguaje, además de la correspondiente arquitectura de cada procesador. Lo cual hace que la curva de aprendizaje sea grandísima y con un espectro de aplicación limitado.

Por eso nace la idea de HASM, un lenguaje de programación en bajo nivel que recupera la esencia de los lenguajes de alto nivel como c, basic o python, así como lenguajes de marcas como XML, para llevarlos a una estructura de programación a bajo nivel homogenea y universal.

De esta manera, las reglas del lenguaje están claras, así que sólo hay que limitarse a las diferencias y peculiaridades de la arquitectura, y no al lenguaje propiamente dicho.

## Diccionarios

Las arquitecturas y funcionalidades de cada dispositivo están definidas en una serie de diccionarios estructurados de la siguiente manera:

### harch: Arquitecturas

Este fichero define metainformación de la arquitectura, así como el banco de registros interno.

### hpack: Packages

Este diccionario define los distintos empaquetados del dispositivo, así como características técnicas y su pinout.

### hdec: Decodificador

Este es el más importante, ya que define mediante tablas todas las operaciones disponibles, así como su distribución y equivalencias en HASM.

### hopc: Tablas de Opcodes

Con la tabla anterior se genera mediante producto cartesiano todas las tablas de opcodes, que son las que utiliza el compilador para procesar el lenguaje.

### hsys: Arquitectura de Sistemas

En este otro diccionario se definen todos los hardwares y periféricos que utilizan un determinado dispositivo, y se declaran todas las peculiaridades del sistema, como interrupciones, direcciones de memoria, así como información técnica.

### halias: Diccionarios de alias

Esta es una parte muy potente de hasm, ya que permite redefinir palabras clave del lenguaje o instrucciones, permitiendo flexibilizarlo hasta el punto de poder programar en ensamblador con apariencia de basic, en español, o incluso con emojis.

Esto posibilita múltiples opciones muy interesantes, que van desde la parte educativa y el aprendizaje, la personalización del lenguaje y hasta la programación en equipo en diferentes idiomas. Incluso sirve para preservar seguridad para el código propietario, ya que se puede utilizar para ofuscar el código fuente.

Los diccionarios son traducibles unos entre otros y están ordenados jerárquicamente.