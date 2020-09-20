---
layout: article
title: Procesos en Racket.
date: 2020-09-19 15:33:00+0200
coverPhoto: https://superawesomevectors.com/wp-content/uploads/2017/07/abacus-free-flat-vector-icon-800x566.jpg
---

En el presente artículo se presenta cómo es posible por medio de Scheme escribir procesos que realicen computaciones numéricas. **En especial fórmulas recursivas**, algoritmos que se definen en términos de sí mismos.

Ahora, unas notas previas:
- Las funciones `define` y `cond` son los principales mecanismos usados para la construcción y abstracción de funciones. 

- La recursividad es un elemento importante de control.

- Se pueden modelar funciones y expresiones matemáticas con facilidad usando los elementos anteriores.

- Para facilitar el proceso de programación en código de un problema se debe dividir en subproblemas más pequeños y combinarlos.

- Cuando se construye un programa es importante estudiar el tiempo que tarda en ejecutarse. Esta es el área de estudio del análisis de algoritmos.

El poder de este tipo de descripciones consiste fundamentalmente en el hecho de poder descomponer un problema en uno nuevo que sea matemáticamente más sencillo que el anterior. Se desea hacer un proceso de reducción continua hasta que se llegue a un caso inicial sencillo de resolver.

Por ejemplo, una operación como elevar a una potencia a un número es fácilmente interpretable como una función recursiva.

$$2^5 = 2 \cdot (2^4) \newline 2^5 = 2 \cdot (2 \cdot (2^3)) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot (2^2))) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot (2 \cdot (2^1)))) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot (2 \cdot (2 \cdot (2^0))))) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot (2 \cdot (2 \cdot (1))))) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot (2 \cdot (2 )))) \newline 2^5 = 2 \cdot (2 \cdot (2 \cdot ( 4 ))) \newline 2^5 = 2 \cdot (2 \cdot (8)) \newline 2^5 = 2 \cdot (16) \newline 2^5 = 32 \newline$$

En la representación anterior se muestra muy bien cómo la recursividad de pila hace su trabajo al llamarse a sí misma hasta que encuentra un caso base (exponente 0). Después, sólo retorna el resultado en cada llamada.

A continuación, un ejemplo de cómo se podría representar en Racket:
```
;; Potencia de un numero entero.
(define (potencia num exponente)
  (cond ((equal? exponente 0)
        1)
  (else
   (* num (potencia num (- exponente 1))))))  
```

De igual manera, muchas operaciones matemáticas como la sumatoria, factorial, Fibonacci, etc. pueden ser representados por este método. Esto es debido principalmente a que utilizan la misma operación sobre su siguiente parámetro. En casos así es que la recursividad brilla.
$$\sum\limits_{i=0}^4 i^3 = 0^3 + 1^3 + 2^3 + 3^3 + 4^3$$

Ahora bien, rara vez nos enfrentamos a problemas tan sencillos como realizar únicamente una operación. La expresión anterior en la que se suman los resultados de varias potencias puede servir de ejemplo. 

Racket permite usar la expresión **`fun`** para indicar que se operará sobre cualquier función que permitas estas operaciones. Creo que lo puse en palabras complicadas. Veámoslo así: en la suma anterior ocurren dos operaciones (potencia y suma) pero podrían ser diferentes, como esta:
$$
\sum\limits_{i=1}^5 i! = 1! + 2! + 3! + 4! + 5!
$$
En esta se opera entre la suma y la función factorial. Ahora, veamos el código:

```
;; Sumatoria de los resultados de una funcion fun.
(define (sumarFun fun num)
  (cond ((equal? num 0)
        (fun 0))
  (else
   (+ (fun num) (sumarFun fun (- num 1))))))
```

y se usa como así:
```python
> (sumarFun factorial 5)
154
```
Claro que no todo es amor, por la manera en que está definida la función `sumarFun` sólo nos permitirá recibir un parámetro. Por lo tanto, sólo aceptará funciones que acepten un parámetro. Veamos este otro ejemplo:
```python
> (sumarFun potencia 2 5)
 sumarFun: arity mismatch;
 the expected number of arguments does not match the given number
  expected: 2
  given: 3
  arguments...:
```

-----
**Referencia:** *Introducción a la programación con Scheme por José E. Helo Guzmán.*

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)
