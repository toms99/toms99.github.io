---
layout: article
title: Lenguajes y paradigmas de programación
date: 2020-09-15 
author: Tomás Segura
coverPhoto: https://pbs.twimg.com/profile_images/1011277014924496897/aTMLLVVZ_400x400.jpg
---

Los lenguajes de programación formales se comenzaron a diseñar a partir de los años 50. Su estudio tiene como objetivo **diseñar lenguajes que combinen poder expresivo con simplicidad y eficiencia.**

Al incio de su desarrollo se desconocía si una traducción automática entre un lenguaje orientado a usuarios y un lenguaje máquina era factible. A partir de ese entonces muchos lenguajes han surgido combinando conceptos de lenguajes anteriores con nuevos enfoques.

**Los lenguajes actuales no deben considerarse como el producto último y definitivo del diseño de lenguajes.** Nuevos conceptos y paradigmas aún hoy se están desarrollando.

![Keep Learning quote](https://quotefancy.com/media/wallpaper/3840x2160/627934-Jane-Fonda-Quote-Stay-curious-keep-learning-and-keep-growing-And.jpg)

El objetivo del curso es programar en los lenguajes más significtivos de los diferentes paradigmas.

### ¿Por qué estudiar lenguajes de programación?
- Mejora la habilidad para desarrollar algoritos eficaces.
- Mejora el uso del lenguaje de programación disponible.
- Mejorar la capacidad para escoger el lenguaje en que se programará un proyecto.
- Facilitar el aprendizaje de un nuevo lenguaje.
- Facilitar el diseño de un nuevo lenguaje.

### Requisitos principales de un lenguaje.
- **Universal**. Cualquier problema que se pueda resolver en una computadora debe poder ser resuelto en el lenguaje.
- **Natural**. Debe facilitar la resolución de problemas al menos para el área de aplicación del lenguaje.
- **Implementable**. Debe ser posible implementar todo programa bien formado en dicho lenguaje.

### Sintaxis vs Semántica.
**Sintaxis**. Las reglas y su cumplimiento. Se refiere a la forma de los programas; cómo los diferentes componentes del lenguaje son agregados para formar programas. Afecta en cómo los programas son escritos por los programadores, cómo son leídos por otros programadores y cómo se hace parsing de ellos.
 
**Semántica**. Significado de los programas. Cómo se comportan cuando son ejecutados. Determina cómo los programas son compuestos por los programadores. 

### Procesadores de lenguaje.
Cualquier sistema para procesamiento de programas, ejecución de programas o cómo se preparan dichos programas para ejecución. Incluyen:
- Compiladores.
- Intérpretes.
- Herramientas auxiliares como editores de código fuente y debuggers.

### Programas de alto y bajo nivel.
**El nivel se refiere principalmente a la facilidad de un algoritmo para la cognitiva humana** en lugar de las máquinas. 

Los programas de alto nivel se caracterizan por expresar el algoritmo de una manera sencilla. Son independientes de la máquina sobre la que se ejecutan. Son compilados en lenguaje de máquina o son interpretados de manera directa o una combinación de ambos.

## Paradigmas de programación

### Imperativo.
Uso de comandos para actualizar variables. Caracterizado por el uso de variables, comando y procedimientos.

### Orientado a Objetos (POO).
Las variables pueden ser accedidas únicamente por medio de operaciones asociadas a ellas. Caracterizado por el uso de objetos clases y herencia.

### Funcional.
Hace uso de funciones como objetos de primera clase e incorporan avanzados sistemas de tipos. Se basan en funciones sobre listas y árboles, permiten resolver problemas significativos sin utilizar variables.

### Lógico.
Uso de principios lógicos para hacer deducciones que resuelven problemas. Se caracteriza por el uso de relaciones. Están basados en un subconjunto de la lógica matemática. El computador **infiere asociaciones entre valores en lugar de calcular valores de salida a partir de valores de entrada.**

## Lenguajes de programación.

### Fortran (Formula Translating System).
- Introdujo las expresiones simbólicas, arreglos y procedimientos.
- Desarrollado por IBM en 1957.
- Introdujo los subprogramas con parámetros.
- En su forma original era considerado de bastante bajo nivel. Sus flujos de control eran bastante afectados por saltos de condicionales y no condicionales (instrucciones jmp disfrazadas).
- Su última versión fue estandarizada en 1997.

### Cobol (Common Business Oriented Language).
- Fue creado en el año 1959.
- Introdujo el concepto de descripción de datos.
- Introdujo la idea de un lenguaje con un área de aplicación no numérica.
- Su última versión fue estandarizada en el 2002.
- En aquellos tiempos los lenguajes estaban orientados a la mate y las ciencias pero cobol fue diseñado para escribir  sistemas más empresariales.


### Algol 60 (Algorithmic Language).
- Fue creado en el año 1960 sucesor de Algol creado en 1958.
- Primer lenguaje de programación diseñado para comunicarse por medio de algoritmos y no solo para programar una computadora.
- Introduce la estructura de bloques que permite declarar los elementos cuando el programa los necesita y no solo al inicio.
- Ha tenido una gran influencia en muchos lenguajes: CPL, BCPL, Simula, Pascal.


### PL/I (Programming Language 1).
- Fue propuesto por IBM hacia 1970.
- Combina la capacidad numérica de FORTRAN y Algol con las habilidades de procesamiento de datos de COBOL.
- Introdujo formas de bajo nivel para manejar excepciones y concurrencia.
- El resultado fue un lenguaje muy grande complejo, incoherente y difícil de programar.

### Pascal
- Fue creado por el profesor suizo Nicklaus Wirth entre los años 1968 y 1969.
- Es el más popular de los programas Algo-like debido a su simpleza, sistematización e implementación eficiente.
- De los primeros en tener una gran riqueza en estructura de control, tipos de datos y definiciones de datos.
- Su éxito se debe a que **estaba diseñado para un área especifica, la enseñanza de los principios de programación.**


> **Tip del profe**: Siempre investigar opciones diferentes para desarrollar los programas, tener iniciativas para probar nuevas tecnologías. Siempre justificar bien las herramientas.


### C
- Fue desarrollado por Dennis Ritchie entre 1969 y 1972.
- Originalmente diseñado para ser el lenguaje de programación para UNIX.
- Sirve para programar tanto a bajo como alto nivel.
- Sus características de bajo nivel son fácilmente mal utilizados resultando en sistemas no portables y difíciles de mantener.

### C++
- Fue diseñado a mediados de los años 1980 por Bjarne Stroustrup.
- La intención de su creación fue el extender al lenguaje de programación C mecanismos que permiten la manipulación de objetos.
- Unió las comunidades de orientación a objetos con C, lo que lo hizo muy popular.

### Java
- Fue diseñado simplificando C++ de manera drástica.
- A pesar de ser un simple lenguaje orientado a objetos, puede ser utilizado para programación distribuida y concurrente.
- Posee una implementación altamente portable gracias a su máquina virtual.

## LISP
- Fue especificado originalmente en 1958 por John McCarthy. 
- Primer lenguaje funcional.
- Basado en funciones sobre listas.
- Soporta variables y asignaciones.
- **Racket está basado en Lisp.**

## Prolog (Programmation en logique).
- Fue ideado a principios de los años 70 en la Universidad de Aix-Marseille I (Marsella, Francia)
- Lenguaje clásico de programación lógica.
- En su forma pura, es muy eficiente por lo que ha sido ampliado con características no lógicas para hacerlo más útil.

------
**Referencia:** *Material de clase del profesor Ing. Marco Rivera Meneses.*

![InfogramaSobreLaHistoriaDeLosLenguajes](https://www.pcs.udel.edu/wp-content/uploads/2019/08/201908-HistoryComputerProg-infographic-TSG-UDEL.jpg)

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)


