# hasm
## Motivación
Human Assembler ha sido creado para establecer una capa de abstracción a bajo nivel de los lenguajes ensambladores de los distintos procesadores, microcontroladores, unidades de coma flotante, y toda clase de dispositivos capaces de computar para un propósito general.

Durante años y décadas han estado regidos por un código muy primitivo y poco evolucionado basado en mnemónicos y opcodes. El objetivo es llegar a la esencia de esos opcodes para crear un lenguaje dinámico, expresivo, fácil de aprender y de mantener, además de ser totalmente personalizable.

Esos mnemónicos, al estar sujetos por los derechos del copyright eran distintos para cada fabricante, por lo que aprender un lenguaje ensamblador en concreto implicaba limitarse no sólo a las especificaciones de dicho procesador, si no también a su implementación del desarrollo de su arquitectura, con palabras claves exclusivas que nada se parecen a las de la competencia.

Eso de cara a la industria, a la educación, al mantenimiento y al desarrollo es un handicap mayúsculo, ya que es necesario aprenderse las peculiaridades de cada lenguaje, además de la correspondiente arquitectura de cada procesador. Lo cual hace que la curva de aprendizaje sea grandísima y con un espectro de aplicación limitado.

Por eso nace la idea de HASM, un lenguaje de programación en bajo nivel que recupera la esencia de los lenguajes de alto nivel como c, basic o python, así como lenguajes de marcas como XML, para llevarlos a una estructura de programación a bajo nivel homogenea y universal.

De esta manera, las reglas del lenguaje están claras, así que sólo hay que limitarse a las diferencias y peculiaridades de la arquitectura, y no al lenguaje propiamente dicho.

## Herramientas

### hasm-vscode

En https://github.com/pekesoft/hasm-vscode podéis encontrar la extensión para el coloreado del lenguaje usando Visual Studio Code.

## Diccionarios

Las arquitecturas y funcionalidades de cada dispositivo están definidas en una serie de diccionarios estructurados de la siguiente manera:

### harch: Arquitecturas

Este fichero define metainformación de la arquitectura, así como el banco de registros interno.

### hpack: Packages

Este diccionario define los distintos empaquetados del dispositivo, así como características técnicas y su pinout.

### hdec: Decodificador

Este es el más importante, ya que define mediante tablas todas las operaciones disponibles, así como su distribución y equivalencias en HASM.

Por el momento estamos trabajando en las tablas de decodificación de Z80 y del PIO de RP2040.

### hopc: Tablas de Opcodes

Con la tabla anterior se genera mediante producto cartesiano todas las tablas de opcodes, que son las que utiliza el compilador para procesar el lenguaje.

### hsys: Arquitectura de Sistemas

En este otro diccionario se definen todos los hardwares y periféricos que utilizan un determinado dispositivo, y se declaran todas las peculiaridades del sistema, como interrupciones, direcciones de memoria, así como información técnica.

### halias: Diccionarios de alias

Esta es una parte muy potente de hasm, ya que permite redefinir palabras clave del lenguaje o instrucciones, permitiendo flexibilizarlo hasta el punto de poder programar en ensamblador con apariencia de basic, en español, o incluso con emojis.

Esto posibilita múltiples opciones muy interesantes, que van desde la parte educativa y el aprendizaje, la personalización del lenguaje y hasta la programación en equipo en diferentes idiomas. Incluso sirve para preservar seguridad para el código propietario, ya que se puede utilizar para ofuscar el código fuente.

Los diccionarios de alias son traducibles unos entre otros y están ordenados jerárquicamente.

## Ejemplos de Código

Con el fin de probar el código de hasm y poder evaluar su gramática, claridad y uso mientras estamos en la fase de investigación y experimentación hemos creado algunos ejemplos reales basados en piezas de código historicas, en el que acompañamos el ensamblador real con la versión traducida a hasm.

Eso, además de permitirnos conocer nuestro propio lenguaje, nos permite además analizarlo de una forma más pragmática, permitiéndonos corregir y cambiar aspectos que a la larga serían odiosos, poco prácticos, o rompería las reglas del lenguaje.

### ZX Spectrum ROM

Se trata de la ROM real del ZX Spectrum de 1982 de Sinclair, ideal para probar el hasm sobre asm de Z80.

### WozMon

Más histórico aun es este código escrito por el gran Steve Wozniak, y que era todo el software que venía incluído en la ROM del legendario Apple-I. Esta pieza es ideal para analizar el hasm sobre asm de 6502. (En Construcción)