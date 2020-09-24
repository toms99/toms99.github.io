﻿﻿---
layout: article
title: Paradigma funcional.
date: 2020-09-16 
author: Tomás Segura
coverPhoto: https://cdn.arstechnica.net/wp-content/uploads/2013/04/recursive-water.jpg
---
La esencia de la programación funcional consiste en la combinación de funciones para producir funciones aún más poderosas.

**Función:** asociación que toma cada elemento de un conjunto (dominio) y le asigna un elemento de otro dominio (Rango).

### Características del paradigma funcional:
- Enfatiza la evaluación de expresiones, antes que la ejecución de comandos.
- Una programación funcional está constituida enteramente por funciones; el programa principal es una función que toma como argumento la entrada al programa y genera la salida del programa como su resultado.
- La función principal se define en términos de otras funciones y estas a su vez, en términos de más funciones; esta cadena finaliza en funciones predefinidas o primitivas.
- La principal diferencia con los programas convencionales es que los únicos elementos constructores en los programas funcionales son la definición y la aplicación de funciones, mientras que en los programas imperativos se utilizan variables, asignaciones, ciclos iterativos, etc. Aunque hoy en día se han extendido los lenguajes funcionales para que sí puedan definiar variables. 
- Se hace mucho uso de la recursividad para la escritura de funciones.
- Tratan las funciones como ciudadanos de primera clase. 
- Tienen operaciones que permiten combinar funciones para crear otras más complejas.

### Potencia de la programación funcional.

#### Manejo de funciones de alto orden.
La principal diferencia con los programas convencionales es que los únicos elementos constructores en los programas funcionales son la definición y la aplicación de funciones, mientras que en los programas imperativos se utilizan variables, asignaciones, ciclos iterativos, etc.

#### Declaración de tipos algebraicos.
Los lenguajes funcionales con tipos como ML y Haskell dan la posibilidad de declarar tipos adicionales a los tipos primitivos.

#### Inferencia de tipos.
Tradicionalmente, los sistemas de tipos de los lenguajes de programación se han dividido en dos: estrictos y no estrictos:

**Estrictos**: el programador debe declarar el tipo de cada una de las variables y de los argumentos de las funciones y procedimientos, y ceñirse de manera estricta a estas declaraciones.

**No estrictos**: El programador no debe ceñirse necesariamente a las declaraciones y eventualmente las puede obviar.

Los sistemas de inferencia de tipos representan un punto intermedio entre los dos esquemas mencionados.

Conservan el carácter estricto del sistema de tipos y por otro liberan al programador de las declaraciones explícitas y de sus valores de retorno.


#### Emparejamiento de patrones.
Se refiere a la posibilidad que brindan algunos lenguajes funcionales de definir funciones por casos; esto le da mayor capacidad expresiva al lenguaje permitiendo escribir el código más claro, sencillo y conciso.
```
Fib(0) = 1
Fib(1) = 1
Fib(x) = Fib (X-1) + Fib (X-2)
```

#### Componentes de un lenuajes funcionales.
Los lenguajes funcionales tienen cinco componentes.
1. Conjunto de operaciones primitivas.
2. Conjunto de formas funcionales que combinan funciones para crear nuevas.
3. La operación de aplicar una función a sus argumentos y producir un valor.
4. Un conjunto de objetos primitivos.
5. Un mecanismo para ligar un nombre con una nueva función.
	- Esto es necesario para definir funciones recursivas.

### Lenguaje FP
Es un lenguaje funcional, simple y puro. Creado por John Backus a principios de los 70s. No tiene variables, todos los datos deben de ser usados literalmente.

Las principales estructuras de datos del lenguaje son los valores de base y las secuencias. Estos valores se construyen a partir de cualquier conjunto de valores atómicos:
- Booleanos: `#t` y `#f`.
- Enteros: `0, 1, 2, ... n`
- Caracteres: `'a, 'b, 'c`

#### Lenguaje Lisp.
Es el lenguaje de programación mas cercano a un lenguaje funcional. Especificado originalmente en 1958 por John McCarthy. Con el fin de mejorar la eficiencia las versiones actuales de LISP incluyen características no funcionales.

LISP está basado en los principios:
- Provee un conjunto pequeño de primitivas.
- Provee unas pocas pero poderosas facilidades de estructuramiento de datos.

#### Lenguaje Scheme.
Es un dialecto de Lisp. Fue desarrollado por Guy L Steele y Gerald Jay Sussman en la década de los 70’s. 

**Características principales:**
- Proporciona el mínimo número posible de nociones primitivas, construyendo todo lo demás a partir de un reducido número de abstracciones. 
- El mecanismo principal para el control de flujo son las llamadas recursivas.
- Scheme ofrece también gestión automática de memoria (recolección de basura). 
- Las listas son las estructuras básica del lenguaje.

**Ventajas:**
- Es un lenguaje orientado hacia la modelación de problemas. Facilita la abstracción de datos y procesos.
- El pasar de una especificación formal hacia el desarrollo de un programa es relativamente sencillo.
- Posee una base matemática sólida, el cálculo lambda. De esta forma, las pruebas de correctitud de programas son mucho mas fáciles.
- Usualmente los programas escritos en este lenguaje son muchos más cortos, lo cual permiten un mayor nivel de perfeccionamiento y mantenimiento.

---
*Referencia:* Material de clase del profesor Ing. Marco Rivera Meneses.

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)

